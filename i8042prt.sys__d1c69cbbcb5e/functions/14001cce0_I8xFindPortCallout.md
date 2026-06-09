# I8xFindPortCallout

- ea: `0x14001cce0`
- end: `0x14001ce66`
- name: `I8xFindPortCallout`
- size: `390`
- prototype: `NTSTATUS __stdcall(PVOID Context, PUNICODE_STRING PathName, INTERFACE_TYPE BusType, ULONG BusNumber, PKEY_VALUE_FULL_INFORMATION *BusInformation, CONFIGURATION_TYPE ControllerType, ULONG ControllerNumber, PKEY_VALUE_FULL_INFORMATION *ControllerInformation, CONFIGURATION_TYPE PeripheralType, ULONG PeripheralNumber, PKEY_VALUE_FULL_INFORMATION *PeripheralInformation)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140004530`
- `0x140007b10`
- `0x14000cd68`
- `0x14001cce0`
- `0x14001cfa0`

## pseudocode

```c
__int64 __fastcall I8xFindPortCallout(
        _DWORD *Context,
        unsigned __int64 PathName,
        __int64 BusType,
        __int64 BusNumber,
        PKEY_VALUE_FULL_INFORMATION *BusInformation,
        CONFIGURATION_TYPE ControllerType,
        ULONG ControllerNumber,
        PKEY_VALUE_FULL_INFORMATION *ControllerInformation)
{
  __int64 v9; // rsi
  unsigned int v10; // edi
  PKEY_VALUE_FULL_INFORMATION v11; // rbx
  __int64 DataOffset; // rax
  unsigned int v13; // ebp
  char *v14; // rsi
  unsigned int v15; // r15d
  unsigned __int8 *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-68h]
  __int64 v21; // [rsp+28h] [rbp-60h]

  v9 = (unsigned int)Context[1];
  v10 = -1073741823;
  v11 = ControllerInformation[1];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      PathName,
      15,
      26,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  if ( v11->DataLength )
  {
    DataOffset = v11->DataOffset;
    v13 = 0;
    v14 = (char *)&Context[8 * v9 + 2];
    v15 = *(ULONG *)((char *)&v11->DataLength + DataOffset);
    v16 = (unsigned __int8 *)&v11->NameLength + DataOffset;
    if ( v15 )
    {
      do
      {
        PathName = *v16;
        if ( (_DWORD)PathName == 1 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_DDd(
              WPP_GLOBAL_Control->DeviceExtension,
              1,
              BusType,
              BusNumber,
              v20,
              *((_DWORD *)v16 + 2),
              *((_DWORD *)v16 + 1),
              *((_DWORD *)v16 + 3));
          v14[1] = *v16;
          *((_WORD *)v14 + 2) = *((_WORD *)v16 + 1);
          v14[2] = 1;
          *((_DWORD *)v14 + 3) = 1;
          v17 = *((unsigned int *)v16 + 3);
          *((_DWORD *)v14 + 2) = v17;
          v18 = *(_QWORD *)(v16 + 4);
          *((_QWORD *)v14 + 2) = v18;
          *((_QWORD *)v14 + 3) = v17 - 1 + v18;
          ++Context[1];
          I8xRemovePort(v14, PathName, BusType, BusNumber);
          v14 += 32;
          v10 = 0;
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            PathName,
            14,
            28,
            (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
        }
        ++v13;
        v16 += 20;
      }
      while ( v13 < v15 );
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v21) = v10;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      PathName,
      15,
      29,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      v21);
  }
  return v10;
}

```

## disassembly

```asm
0x14001cce0  push    rbx
0x14001cce2  push    rbp
0x14001cce3  push    rsi
0x14001cce4  push    rdi
0x14001cce5  push    r12
0x14001cce7  push    r13
0x14001cce9  push    r14
0x14001cceb  push    r15
0x14001cced  sub     rsp, 48h
0x14001ccf1  mov     rax, [rsp+88h+ControllerInformation]
0x14001ccf9  mov     r14, rcx
0x14001ccfc  mov     esi, [rcx+4]
0x14001ccff  mov     edi, 0C0000001h
0x14001cd04  mov     rbx, [rax+8]
0x14001cd08  lea     r12, WPP_RECORDER_INITIALIZED
0x14001cd0f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001cd16  lea     r13, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14001cd1d  jz      short loc_14001CD3E
0x14001cd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd26  mov     r9d, 1Ah
0x14001cd2c  mov     [rsp+88h+var_68], r13
0x14001cd31  mov     rcx, [rcx+40h]
0x14001cd35  lea     r8d, [r9-0Bh]
0x14001cd39  call    WPP_RECORDER_SF_
0x14001cd3e  cmp     dword ptr [rbx+0Ch], 0
0x14001cd42  jz      loc_14001CE26
0x14001cd48  mov     eax, [rbx+8]
0x14001cd4b  xor     ebp, ebp
0x14001cd4d  shl     rsi, 5
0x14001cd51  add     rsi, 8
0x14001cd55  add     rsi, r14
0x14001cd58  mov     r15d, [rax+rbx+0Ch]
0x14001cd5d  add     rbx, 10h
0x14001cd61  add     rbx, rax
0x14001cd64  test    r15d, r15d
0x14001cd67  jz      loc_14001CE26
0x14001cd6d  movzx   edx, byte ptr [rbx]
0x14001cd70  cmp     edx, 1
0x14001cd73  jz      short loc_14001CDA7
0x14001cd75  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001cd7c  jz      loc_14001CE17
0x14001cd82  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd89  mov     r9d, 1Ch
0x14001cd8f  mov     dword ptr [rsp+88h+var_60], edx
0x14001cd93  mov     [rsp+88h+var_68], r13
0x14001cd98  mov     rcx, [rcx+40h]
0x14001cd9c  lea     r8d, [r9-0Eh]
0x14001cda0  call    WPP_RECORDER_SF_D
0x14001cda5  jmp     short loc_14001CE17
0x14001cda7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001cdae  jz      short loc_14001CDD5
0x14001cdb0  mov     eax, [rbx+0Ch]
0x14001cdb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cdba  mov     [rsp+88h+var_50], eax
0x14001cdbe  mov     eax, [rbx+4]
0x14001cdc1  mov     [rsp+88h+var_58], eax
0x14001cdc5  mov     eax, [rbx+8]
0x14001cdc8  mov     rcx, [rcx+40h]
0x14001cdcc  mov     dword ptr [rsp+88h+var_60], eax
0x14001cdd0  call    WPP_RECORDER_SF_DDd
0x14001cdd5  mov     al, [rbx]
0x14001cdd7  mov     [rsi+1], al
0x14001cdda  movzx   eax, word ptr [rbx+2]
0x14001cdde  mov     [rsi+4], ax
0x14001cde2  mov     byte ptr [rsi+2], 1
0x14001cde6  mov     dword ptr [rsi+0Ch], 1
0x14001cded  mov     eax, [rbx+0Ch]
0x14001cdf0  mov     [rsi+8], eax
0x14001cdf3  dec     rax
0x14001cdf6  mov     rcx, [rbx+4]
0x14001cdfa  mov     [rsi+10h], rcx
0x14001cdfe  add     rcx, rax
0x14001ce01  mov     [rsi+18h], rcx
0x14001ce05  mov     rcx, rsi
0x14001ce08  inc     dword ptr [r14+4]
0x14001ce0c  call    I8xRemovePort
0x14001ce11  add     rsi, 20h ; ' '
0x14001ce15  xor     edi, edi
0x14001ce17  inc     ebp
0x14001ce19  add     rbx, 14h
0x14001ce1d  cmp     ebp, r15d
0x14001ce20  jb      loc_14001CD6D
0x14001ce26  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ce2d  jz      short loc_14001CE52
0x14001ce2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce36  mov     r9d, 1Dh
0x14001ce3c  mov     dword ptr [rsp+88h+var_60], edi
0x14001ce40  mov     [rsp+88h+var_68], r13
0x14001ce45  mov     rcx, [rcx+40h]
0x14001ce49  lea     r8d, [r9-0Eh]
0x14001ce4d  call    WPP_RECORDER_SF_D
0x14001ce52  mov     eax, edi
0x14001ce54  add     rsp, 48h
0x14001ce58  pop     r15
0x14001ce5a  pop     r14
0x14001ce5c  pop     r13
0x14001ce5e  pop     r12
0x14001ce60  pop     rdi
0x14001ce61  pop     rsi
0x14001ce62  pop     rbp
0x14001ce63  pop     rbx
0x14001ce64  retn
```
