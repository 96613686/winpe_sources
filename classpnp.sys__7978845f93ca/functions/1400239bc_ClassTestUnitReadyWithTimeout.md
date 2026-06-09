# ClassTestUnitReadyWithTimeout

- ea: `0x1400239bc`
- end: `0x140023bbb`
- name: `ClassTestUnitReadyWithTimeout`
- size: `511`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PSCSI_REQUEST_BLOCK Srb)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400229f8`

## callees

- `0x14000de10`
- `0x140015bf0`
- `0x1400239bc`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140023b7d`
- `ntoskrnl!KeDelayExecutionThread` at `0x140023b7d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023b5b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023b5b`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140023b2e`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140023b2e`

## pseudocode

```c
__int64 __fastcall ClassTestUnitReadyWithTimeout(PDEVICE_OBJECT DeviceObject, PSCSI_REQUEST_BLOCK Srb)
{
  unsigned int *p_TimeOutValue; // rsi
  unsigned __int64 i; // rbp
  char v6; // r10
  __int64 j; // r9
  __int64 v8; // rcx
  unsigned __int64 DataTransferLength; // r8
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // ecx
  unsigned __int8 *Cdb; // r8
  unsigned int SrbExtension; // edi
  __int64 v15; // r10
  char v16; // r11
  __int64 v17; // rcx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  unsigned __int8 *v22; // rcx
  NTSTATUS v23; // edi
  __int64 v24; // r8
  unsigned __int64 QpcTimeStamp; // [rsp+60h] [rbp+18h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+68h] [rbp+20h] BYREF

  QpcTimeStamp = 0;
  p_TimeOutValue = &Srb->TimeOutValue;
  for ( i = 0; i < 0x23C34600; i += ClasspCalculateTimeDifferenceIn100ns(QpcTimeStamp, 0, v24) )
  {
    if ( Srb->Function == 40 )
    {
      p_TimeOutValue = &Srb->TimeOutValue;
      if ( !Srb->TimeOutValue )
      {
        v6 = 0;
        for ( j = 0; (unsigned int)j < LODWORD(Srb->SrbExtension); j = (unsigned int)(j + 1) )
        {
          v8 = *((unsigned int *)&Srb[1].SenseInfoBuffer + j);
          if ( (unsigned int)v8 >= 0x80 )
          {
            DataTransferLength = Srb->DataTransferLength;
            if ( (unsigned int)v8 < (unsigned int)DataTransferLength )
            {
              v10 = (unsigned int)v8;
              v11 = *(_DWORD *)((char *)&Srb->Length + v8) - 64;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  if ( v12 == 1 && v10 + 40 <= DataTransferLength )
                    break;
                }
                else if ( v10 + 56 <= DataTransferLength )
                {
                  v6 = 1;
                  *(&Srb->CdbLength + v10) = 6;
                }
              }
              else if ( v10 + 40 <= DataTransferLength )
              {
                *(&Srb->CdbLength + v10) = 6;
                break;
              }
              if ( v6 )
                break;
            }
          }
        }
      }
    }
    else
    {
      Srb->CdbLength = 6;
    }
    if ( Srb->Function != 40 )
    {
      Cdb = Srb->Cdb;
      p_TimeOutValue = &Srb->TimeOutValue;
      goto LABEL_43;
    }
    Cdb = 0;
    if ( !*p_TimeOutValue )
    {
      SrbExtension = (unsigned int)Srb->SrbExtension;
      if ( SrbExtension )
      {
        v15 = 0;
        v16 = 0;
        do
        {
          v17 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v15);
          if ( (unsigned int)v17 >= 0x80 )
          {
            v18 = Srb->DataTransferLength;
            if ( (unsigned int)v17 < (unsigned int)v18 )
            {
              v19 = (unsigned int)v17;
              v20 = *(_DWORD *)((char *)&Srb->Length + v17) - 64;
              if ( v20 )
              {
                v21 = v20 - 1;
                if ( v21 )
                {
                  if ( v21 == 1 && v19 + 40 <= v18 )
                  {
                    v22 = (unsigned __int8 *)&Srb->SenseInfoBuffer + v19;
                    if ( !*(unsigned int *)((char *)&Srb->SrbFlags + v19) )
                      v22 = Cdb;
                    Cdb = v22;
                    break;
                  }
                }
                else if ( v19 + 56 <= v18 )
                {
                  if ( !*(&Srb->CdbLength + v19) )
                    break;
                  v16 = 1;
                  Cdb = (unsigned __int8 *)&Srb->DataBuffer + v19;
                }
              }
              else if ( v19 + 40 <= v18 )
              {
                if ( *(&Srb->CdbLength + v19) )
                  Cdb = (unsigned __int8 *)&Srb->DataBuffer + v19;
                break;
              }
              if ( v16 )
                break;
            }
          }
          v15 = (unsigned int)(v15 + 1);
        }
        while ( (unsigned int)v15 < SrbExtension );
      }
    }
LABEL_43:
    *Cdb = 0;
    QpcTimeStamp = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
    v23 = ClassSendSrbSynchronous(DeviceObject, Srb, 0, 0, 0);
    if ( v23 >= 0 )
      break;
    if ( KeGetCurrentIrql() >= 2u )
      break;
    Interval.QuadPart = -10000000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1400239bc  mov     [rsp+arg_0], rbx
0x1400239c1  mov     [rsp+arg_8], rbp
0x1400239c6  push    rsi
0x1400239c7  push    rdi
0x1400239c8  push    r14
0x1400239ca  sub     rsp, 30h
0x1400239ce  mov     rbx, rdx
0x1400239d1  mov     [rsp+48h+QpcTimeStamp], 0
0x1400239da  mov     r14, rcx
0x1400239dd  lea     rsi, [rdx+14h]
0x1400239e1  xor     ebp, ebp
0x1400239e3  cmp     byte ptr [rbx+2], 28h ; '('
0x1400239e7  jnz     short loc_140023A66
0x1400239e9  lea     rsi, [rbx+14h]
0x1400239ed  cmp     dword ptr [rsi], 0
0x1400239f0  jnz     short loc_140023A6A
0x1400239f2  xor     r10b, r10b
0x1400239f5  xor     r9d, r9d
0x1400239f8  cmp     [rbx+38h], r9d
0x1400239fc  jbe     short loc_140023A6A
0x1400239fe  mov     ecx, [rbx+r9*4+78h]
0x140023a03  cmp     ecx, 80h
0x140023a09  jb      short loc_140023A54
0x140023a0b  mov     r8d, [rbx+10h]
0x140023a0f  cmp     ecx, r8d
0x140023a12  jnb     short loc_140023A54
0x140023a14  mov     edx, ecx
0x140023a16  mov     ecx, [rcx+rbx]
0x140023a19  sub     ecx, 40h ; '@'
0x140023a1c  jz      short loc_140023A46
0x140023a1e  sub     ecx, 1
0x140023a21  jz      short loc_140023A33
0x140023a23  cmp     ecx, 1
0x140023a26  jnz     short loc_140023A4F
0x140023a28  lea     rcx, [rdx+28h]
0x140023a2c  cmp     rcx, r8
0x140023a2f  jbe     short loc_140023A6A
0x140023a31  jmp     short loc_140023A4F
0x140023a33  lea     rcx, [rdx+38h]
0x140023a37  cmp     rcx, r8
0x140023a3a  ja      short loc_140023A4F
0x140023a3c  mov     r10b, 1
0x140023a3f  mov     byte ptr [rdx+rbx+0Ah], 6
0x140023a44  jmp     short loc_140023A4F
0x140023a46  lea     rcx, [rdx+28h]
0x140023a4a  cmp     rcx, r8
0x140023a4d  jbe     short loc_140023A5F
0x140023a4f  test    r10b, r10b
0x140023a52  jnz     short loc_140023A6A
0x140023a54  inc     r9d
0x140023a57  cmp     r9d, [rbx+38h]
0x140023a5b  jb      short loc_1400239FE
0x140023a5d  jmp     short loc_140023A6A
0x140023a5f  mov     byte ptr [rdx+rbx+0Ah], 6
0x140023a64  jmp     short loc_140023A6A
0x140023a66  mov     byte ptr [rbx+0Ah], 6
0x140023a6a  cmp     byte ptr [rbx+2], 28h ; '('
0x140023a6e  jnz     loc_140023B1D
0x140023a74  xor     r8d, r8d
0x140023a77  cmp     [rsi], r8d
0x140023a7a  jnz     loc_140023B25
0x140023a80  mov     edi, [rbx+38h]
0x140023a83  test    edi, edi
0x140023a85  jz      loc_140023B25
0x140023a8b  xor     r10d, r10d
0x140023a8e  xor     r11b, r11b
0x140023a91  mov     ecx, [rbx+r10*4+78h]
0x140023a96  cmp     ecx, 80h
0x140023a9c  jb      short loc_140023B03
0x140023a9e  mov     r9d, [rbx+10h]
0x140023aa2  cmp     ecx, r9d
0x140023aa5  jnb     short loc_140023B03
0x140023aa7  mov     edx, ecx
0x140023aa9  mov     ecx, [rcx+rbx]
0x140023aac  sub     ecx, 40h ; '@'
0x140023aaf  jz      short loc_140023AF5
0x140023ab1  sub     ecx, 1
0x140023ab4  jz      short loc_140023AD9
0x140023ab6  cmp     ecx, 1
0x140023ab9  jnz     short loc_140023AFE
0x140023abb  lea     rcx, [rdx+28h]
0x140023abf  cmp     rcx, r9
0x140023ac2  ja      short loc_140023AFE
0x140023ac4  lea     rcx, [rbx+20h]
0x140023ac8  add     rcx, rdx
0x140023acb  cmp     dword ptr [rdx+rbx+0Ch], 0
0x140023ad0  cmovz   rcx, r8
0x140023ad4  mov     r8, rcx
0x140023ad7  jmp     short loc_140023B25
0x140023ad9  lea     rcx, [rdx+38h]
0x140023add  cmp     rcx, r9
0x140023ae0  ja      short loc_140023AFE
0x140023ae2  cmp     byte ptr [rdx+rbx+0Ah], 0
0x140023ae7  jbe     short loc_140023B25
0x140023ae9  lea     r8, [rbx+18h]
0x140023aed  mov     r11b, 1
0x140023af0  add     r8, rdx
0x140023af3  jmp     short loc_140023AFE
0x140023af5  lea     rcx, [rdx+28h]
0x140023af9  cmp     rcx, r9
0x140023afc  jbe     short loc_140023B0D
0x140023afe  test    r11b, r11b
0x140023b01  jnz     short loc_140023B25
0x140023b03  inc     r10d
0x140023b06  cmp     r10d, edi
0x140023b09  jb      short loc_140023A91
0x140023b0b  jmp     short loc_140023B25
0x140023b0d  cmp     byte ptr [rdx+rbx+0Ah], 0
0x140023b12  jbe     short loc_140023B25
0x140023b14  lea     r8, [rbx+18h]
0x140023b18  add     r8, rdx
0x140023b1b  jmp     short loc_140023B25
0x140023b1d  lea     r8, [rbx+48h]
0x140023b21  lea     rsi, [rbx+14h]
0x140023b25  lea     rcx, [rsp+48h+QpcTimeStamp]; QpcTimeStamp
0x140023b2a  mov     byte ptr [r8], 0
0x140023b2e  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140023b35  nop     dword ptr [rax+rax+00h]
0x140023b3a  xor     r9d, r9d; BufferLength
0x140023b3d  mov     [rsp+48h+WriteToDevice], 0; WriteToDevice
0x140023b42  xor     r8d, r8d; BufferAddress
0x140023b45  mov     [rsp+48h+QpcTimeStamp], rax
0x140023b4a  mov     rdx, rbx; Srb
0x140023b4d  mov     rcx, r14; DeviceObject
0x140023b50  call    ClassSendSrbSynchronous
0x140023b55  mov     edi, eax
0x140023b57  test    eax, eax
0x140023b59  jns     short loc_140023BA5
0x140023b5b  call    cs:__imp_KeGetCurrentIrql
0x140023b62  nop     dword ptr [rax+rax+00h]
0x140023b67  cmp     al, 2
0x140023b69  jnb     short loc_140023BA5
0x140023b6b  lea     r8, [rsp+48h+Interval]; Interval
0x140023b70  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFF676980h
0x140023b79  xor     edx, edx; Alertable
0x140023b7b  xor     ecx, ecx; WaitMode
0x140023b7d  call    cs:__imp_KeDelayExecutionThread
0x140023b84  nop     dword ptr [rax+rax+00h]
0x140023b89  mov     rcx, [rsp+48h+QpcTimeStamp]
0x140023b8e  xor     edx, edx
0x140023b90  call    ClasspCalculateTimeDifferenceIn100ns
0x140023b95  add     rbp, rax
0x140023b98  cmp     rbp, 23C34600h
0x140023b9f  jb      loc_1400239E3
0x140023ba5  mov     rbx, [rsp+48h+arg_0]
0x140023baa  mov     eax, edi
0x140023bac  mov     rbp, [rsp+48h+arg_8]
0x140023bb1  add     rsp, 30h
0x140023bb5  pop     r14
0x140023bb7  pop     rdi
0x140023bb8  pop     rsi
0x140023bb9  retn
```
