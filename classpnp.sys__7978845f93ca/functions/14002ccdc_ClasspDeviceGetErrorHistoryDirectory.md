# ClasspDeviceGetErrorHistoryDirectory

- ea: `0x14002ccdc`
- end: `0x14002cf18`
- name: `ClasspDeviceGetErrorHistoryDirectory`
- size: `572`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002cf20`

## callees

- `0x14000de10`
- `0x14002ccdc`
- `0x14003e940`

## pseudocode

```c
__int64 __fastcall ClasspDeviceGetErrorHistoryDirectory(__int64 a1, __int64 a2, void *a3, ULONG a4)
{
  __int64 v4; // r15
  bool v8; // zf
  int v9; // eax
  char v10; // r10
  __int64 i; // r9
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  char v17; // si
  __int64 v18; // r8
  unsigned int v19; // edi
  __int64 v20; // r10
  char v21; // r11
  __int64 v22; // rcx
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // rcx
  unsigned int v28; // ecx
  int v29; // eax
  __int64 v30; // rdi
  NTSTATUS v31; // eax

  v4 = *(_QWORD *)(a1 + 64);
  memset(a3, 0, a4);
  v8 = *(_BYTE *)(a2 + 2) == 40;
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    *(_DWORD *)(a2 + 32) = 255;
    *(_WORD *)(a2 + 38) = 32;
  }
  else
  {
    *(_WORD *)(a2 + 8) = 8447;
  }
  v9 = *(_DWORD *)(v4 + 592);
  if ( v8 )
  {
    v8 = *(_DWORD *)(a2 + 20) == 0;
    *(_DWORD *)(a2 + 24) = v9;
    if ( v8 )
    {
      v10 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 56); i = (unsigned int)(i + 1) )
      {
        v12 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v12 >= 0x80 )
        {
          v13 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v12 < (unsigned int)v13 )
          {
            v14 = (unsigned int)v12;
            v15 = *(_DWORD *)(v12 + a2) - 64;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 == 1 && v14 + 40 <= v13 )
                  break;
              }
              else if ( v14 + 56 <= v13 )
              {
                v10 = 1;
                *(_BYTE *)(v14 + a2 + 10) = 16;
              }
            }
            else if ( v14 + 40 <= v13 )
            {
              *(_BYTE *)(v14 + a2 + 10) = 16;
              break;
            }
            if ( v10 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_DWORD *)(a2 + 12) = v9;
    *(_BYTE *)(a2 + 10) = 16;
  }
  v17 = *(_BYTE *)(a2 + 2);
  if ( v17 != 40 )
  {
    v18 = a2 + 72;
    goto LABEL_45;
  }
  v18 = 0;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v19 = *(_DWORD *)(a2 + 56);
    if ( v19 )
    {
      v20 = 0;
      v21 = 0;
      do
      {
        v22 = *(unsigned int *)(a2 + 4 * v20 + 120);
        if ( (unsigned int)v22 >= 0x80 )
        {
          v23 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v22 < (unsigned int)v23 )
          {
            v24 = (unsigned int)v22;
            v25 = *(_DWORD *)(v22 + a2) - 64;
            if ( v25 )
            {
              v26 = v25 - 1;
              if ( v26 )
              {
                if ( v26 == 1 && v24 + 40 <= v23 )
                {
                  v27 = v24 + a2 + 32;
                  if ( !*(_DWORD *)(v24 + a2 + 12) )
                    v27 = v18;
                  v18 = v27;
                  break;
                }
              }
              else if ( v24 + 56 <= v23 )
              {
                if ( !*(_BYTE *)(v24 + a2 + 10) )
                  break;
                v21 = 1;
                v18 = v24 + a2 + 24;
              }
            }
            else if ( v24 + 40 <= v23 )
            {
              if ( *(_BYTE *)(v24 + a2 + 10) )
                v18 = v24 + a2 + 24;
              break;
            }
            if ( v21 )
              break;
          }
        }
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < v19 );
    }
  }
LABEL_45:
  if ( v18 )
  {
    v29 = *(_DWORD *)(v4 + 584);
    if ( v17 == 40 )
      *(_DWORD *)(a2 + 40) = v29;
    else
      *(_DWORD *)(a2 + 20) = v29;
    *(_OWORD *)v18 = 0;
    *(_BYTE *)(v18 + 12) = BYTE1(a4);
    *(_BYTE *)(v18 + 11) = BYTE2(a4);
    v30 = 60;
    *(_BYTE *)(v18 + 10) = HIBYTE(a4);
    *(_WORD *)v18 = 15515;
    *(_BYTE *)(v18 + 13) = a4;
    v31 = ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(v4 + 8), (PSCSI_REQUEST_BLOCK)a2, a3, a4, 0);
    v28 = v31;
    if ( v31 >= 0 )
    {
      if ( *(_BYTE *)(a2 + 2) != 40 )
        v30 = 16;
      if ( *(_DWORD *)(v30 + a2) < 0x20u )
        return (unsigned int)-1073741823;
      return (unsigned int)v31;
    }
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return v28;
}

```

## disassembly

```asm
0x14002ccdc  mov     [rsp+arg_18], r9d
0x14002cce1  push    rbx
0x14002cce2  push    rbp
0x14002cce3  push    rsi
0x14002cce4  push    rdi
0x14002cce5  push    r12
0x14002cce7  push    r13
0x14002cce9  push    r14
0x14002cceb  push    r15
0x14002cced  sub     rsp, 38h
0x14002ccf1  mov     r15, [rcx+40h]
0x14002ccf5  mov     r13, r8
0x14002ccf8  mov     rbx, rdx
0x14002ccfb  mov     r8d, r9d; Size
0x14002ccfe  mov     rcx, r13; void *
0x14002cd01  mov     r12d, r9d
0x14002cd04  xor     edx, edx; Val
0x14002cd06  call    memset
0x14002cd0b  cmp     byte ptr [rbx+2], 28h ; '('
0x14002cd0f  mov     r14d, 20h ; ' '
0x14002cd15  jnz     short loc_14002CD25
0x14002cd17  mov     dword ptr [rbx+20h], 0FFh
0x14002cd1e  mov     [rbx+26h], r14w
0x14002cd23  jmp     short loc_14002CD2B
0x14002cd25  mov     word ptr [rbx+8], 20FFh
0x14002cd2b  mov     eax, [r15+250h]
0x14002cd32  mov     ebp, 10h
0x14002cd37  jnz     short loc_14002CDB6
0x14002cd39  cmp     dword ptr [rbx+14h], 0
0x14002cd3d  mov     [rbx+18h], eax
0x14002cd40  jnz     short loc_14002CDBD
0x14002cd42  xor     r10b, r10b
0x14002cd45  xor     r9d, r9d
0x14002cd48  cmp     [rbx+38h], r9d
0x14002cd4c  jbe     short loc_14002CDBD
0x14002cd4e  mov     ecx, [rbx+r9*4+78h]
0x14002cd53  cmp     ecx, 80h
0x14002cd59  jb      short loc_14002CDA4
0x14002cd5b  mov     r8d, [rbx+10h]
0x14002cd5f  cmp     ecx, r8d
0x14002cd62  jnb     short loc_14002CDA4
0x14002cd64  mov     edx, ecx
0x14002cd66  mov     ecx, [rcx+rbx]
0x14002cd69  sub     ecx, 40h ; '@'
0x14002cd6c  jz      short loc_14002CD96
0x14002cd6e  sub     ecx, 1
0x14002cd71  jz      short loc_14002CD83
0x14002cd73  cmp     ecx, 1
0x14002cd76  jnz     short loc_14002CD9F
0x14002cd78  lea     rcx, [rdx+28h]
0x14002cd7c  cmp     rcx, r8
0x14002cd7f  jbe     short loc_14002CDBD
0x14002cd81  jmp     short loc_14002CD9F
0x14002cd83  lea     rcx, [rdx+38h]
0x14002cd87  cmp     rcx, r8
0x14002cd8a  ja      short loc_14002CD9F
0x14002cd8c  mov     r10b, 1
0x14002cd8f  mov     [rdx+rbx+0Ah], bpl
0x14002cd94  jmp     short loc_14002CD9F
0x14002cd96  lea     rcx, [rdx+28h]
0x14002cd9a  cmp     rcx, r8
0x14002cd9d  jbe     short loc_14002CDAF
0x14002cd9f  test    r10b, r10b
0x14002cda2  jnz     short loc_14002CDBD
0x14002cda4  inc     r9d
0x14002cda7  cmp     r9d, [rbx+38h]
0x14002cdab  jb      short loc_14002CD4E
0x14002cdad  jmp     short loc_14002CDBD
0x14002cdaf  mov     [rdx+rbx+0Ah], bpl
0x14002cdb4  jmp     short loc_14002CDBD
0x14002cdb6  mov     [rbx+0Ch], eax
0x14002cdb9  mov     [rbx+0Ah], bpl
0x14002cdbd  mov     sil, [rbx+2]
0x14002cdc1  cmp     sil, 28h ; '('
0x14002cdc5  jnz     loc_14002CE75
0x14002cdcb  xor     r8d, r8d
0x14002cdce  cmp     [rbx+14h], r8d
0x14002cdd2  jnz     loc_14002CE79
0x14002cdd8  mov     edi, [rbx+38h]
0x14002cddb  test    edi, edi
0x14002cddd  jz      loc_14002CE79
0x14002cde3  xor     r10d, r10d
0x14002cde6  xor     r11b, r11b
0x14002cde9  mov     ecx, [rbx+r10*4+78h]
0x14002cdee  cmp     ecx, 80h
0x14002cdf4  jb      short loc_14002CE5B
0x14002cdf6  mov     r9d, [rbx+10h]
0x14002cdfa  cmp     ecx, r9d
0x14002cdfd  jnb     short loc_14002CE5B
0x14002cdff  mov     edx, ecx
0x14002ce01  mov     ecx, [rcx+rbx]
0x14002ce04  sub     ecx, 40h ; '@'
0x14002ce07  jz      short loc_14002CE4D
0x14002ce09  sub     ecx, 1
0x14002ce0c  jz      short loc_14002CE31
0x14002ce0e  cmp     ecx, 1
0x14002ce11  jnz     short loc_14002CE56
0x14002ce13  lea     rcx, [rdx+28h]
0x14002ce17  cmp     rcx, r9
0x14002ce1a  ja      short loc_14002CE56
0x14002ce1c  lea     rcx, [rbx+20h]
0x14002ce20  add     rcx, rdx
0x14002ce23  cmp     dword ptr [rdx+rbx+0Ch], 0
0x14002ce28  cmovz   rcx, r8
0x14002ce2c  mov     r8, rcx
0x14002ce2f  jmp     short loc_14002CE79
0x14002ce31  lea     rcx, [rdx+38h]
0x14002ce35  cmp     rcx, r9
0x14002ce38  ja      short loc_14002CE56
0x14002ce3a  cmp     byte ptr [rdx+rbx+0Ah], 0
0x14002ce3f  jbe     short loc_14002CE79
0x14002ce41  lea     r8, [rbx+18h]
0x14002ce45  mov     r11b, 1
0x14002ce48  add     r8, rdx
0x14002ce4b  jmp     short loc_14002CE56
0x14002ce4d  lea     rcx, [rdx+28h]
0x14002ce51  cmp     rcx, r9
0x14002ce54  jbe     short loc_14002CE65
0x14002ce56  test    r11b, r11b
0x14002ce59  jnz     short loc_14002CE79
0x14002ce5b  inc     r10d
0x14002ce5e  cmp     r10d, edi
0x14002ce61  jb      short loc_14002CDE9
0x14002ce63  jmp     short loc_14002CE79
0x14002ce65  cmp     byte ptr [rdx+rbx+0Ah], 0
0x14002ce6a  jbe     short loc_14002CE79
0x14002ce6c  lea     r8, [rbx+18h]
0x14002ce70  add     r8, rdx
0x14002ce73  jmp     short loc_14002CE79
0x14002ce75  lea     r8, [rbx+48h]
0x14002ce79  test    r8, r8
0x14002ce7c  jnz     short loc_14002CE85
0x14002ce7e  mov     ecx, 0C0000001h
0x14002ce83  jmp     short loc_14002CF04
0x14002ce85  mov     eax, [r15+248h]
0x14002ce8c  cmp     sil, 28h ; '('
0x14002ce90  jnz     short loc_14002CE97
0x14002ce92  mov     [rbx+28h], eax
0x14002ce95  jmp     short loc_14002CE9A
0x14002ce97  mov     [rbx+14h], eax
0x14002ce9a  mov     al, byte ptr [rsp+78h+arg_18+1]
0x14002cea1  xorps   xmm0, xmm0
0x14002cea4  movups  xmmword ptr [r8], xmm0
0x14002cea8  mov     [r8+0Ch], al
0x14002ceac  mov     r9d, r12d; BufferLength
0x14002ceaf  mov     al, byte ptr [rsp+78h+arg_18+2]
0x14002ceb6  mov     rdx, rbx; Srb
0x14002ceb9  mov     [r8+0Bh], al
0x14002cebd  mov     edi, 3Ch ; '<'
0x14002cec2  mov     al, byte ptr [rsp+78h+arg_18+3]
0x14002cec9  mov     [r8+0Ah], al
0x14002cecd  mov     word ptr [r8], 3C9Bh
0x14002ced3  mov     [r8+0Dh], r12b
0x14002ced7  mov     r8, r13; BufferAddress
0x14002ceda  mov     rcx, [r15+8]; DeviceObject
0x14002cede  mov     [rsp+78h+WriteToDevice], 0; WriteToDevice
0x14002cee3  call    ClassSendSrbSynchronous
0x14002cee8  mov     ecx, eax
0x14002ceea  test    eax, eax
0x14002ceec  js      short loc_14002CF04
0x14002ceee  cmp     byte ptr [rbx+2], 28h ; '('
0x14002cef2  mov     ecx, 0C0000001h
0x14002cef7  cmovnz  rdi, rbp
0x14002cefb  cmp     [rdi+rbx], r14d
0x14002ceff  cmovb   eax, ecx
0x14002cf02  mov     ecx, eax
0x14002cf04  mov     eax, ecx
0x14002cf06  add     rsp, 38h
0x14002cf0a  pop     r15
0x14002cf0c  pop     r14
0x14002cf0e  pop     r13
0x14002cf10  pop     r12
0x14002cf12  pop     rdi
0x14002cf13  pop     rsi
0x14002cf14  pop     rbp
0x14002cf15  pop     rbx
0x14002cf16  retn
```
