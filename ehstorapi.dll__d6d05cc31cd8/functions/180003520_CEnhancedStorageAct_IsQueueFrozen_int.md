# CEnhancedStorageAct::IsQueueFrozen(int *)

- ea: `0x180003520`
- end: `0x18000371d`
- name: `?IsQueueFrozen@CEnhancedStorageAct@@UEAAJPEAH@Z`
- size: `509`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003520`
- `0x180003c54`
- `0x180003ce0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800035f2`
- `KERNEL32!CreateFileW` at `0x1800035f2`
- `KERNEL32!GetLastError` at `0x180003601`
- `KERNEL32!GetLastError` at `0x180003681`
- `KERNEL32!GetLastError` at `0x180003601`
- `KERNEL32!GetLastError` at `0x180003681`
- `KERNEL32!DeviceIoControl` at `0x180003677`
- `KERNEL32!DeviceIoControl` at `0x180003677`
- `KERNEL32!CloseHandle` at `0x180003705`
- `KERNEL32!CloseHandle` at `0x180003705`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageAct::IsQueueFrozen(CEnhancedStorageAct *this, int *a2)
{
  const WCHAR *v4; // rcx
  __int64 v5; // r9
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int8 OutBuffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  OutBuffer = 0;
  BytesReturned = 0;
  if ( a2 )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 8);
    if ( !*((_DWORD *)v4 - 4) )
    {
      v5 = 2147549183LL;
      v6 = -2147418113;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return v6;
      v8 = 34;
      goto LABEL_10;
    }
    FileW = CreateFileW(v4, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return v6;
      v8 = 35;
      v5 = v6;
LABEL_10:
      WPP_SF_d(v7[2], v8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, v5);
      return v6;
    }
    if ( DeviceIoControl(FileW, 0x2D141Cu, 0, 0, &OutBuffer, 1u, &BytesReturned, 0) )
    {
      if ( BytesReturned == 1 )
      {
        v6 = 0;
        *a2 = OutBuffer;
        goto LABEL_29;
      }
      v14 = 2147549183LL;
      v6 = -2147418113;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v13 = 37;
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v13 = 36;
      v14 = v6;
    }
    WPP_SF_d(v12[2], v13, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, v14);
LABEL_29:
    CloseHandle(FileW);
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, "pIsQueueFrozen");
  return 2147942487LL;
}

```

## disassembly

```asm
0x180003520  mov     rax, rsp
0x180003523  mov     [rax+8], rbx
0x180003527  mov     [rax+20h], rsi
0x18000352b  push    rdi
0x18000352c  sub     rsp, 40h
0x180003530  mov     byte ptr [rax+10h], 0
0x180003534  mov     rdi, rdx
0x180003537  mov     dword ptr [rax+18h], 0
0x18000353e  test    rdx, rdx
0x180003541  jnz     short loc_180003580
0x180003543  mov     rcx, cs:WPP_GLOBAL_Control
0x18000354a  lea     rax, WPP_GLOBAL_Control
0x180003551  cmp     rcx, rax
0x180003554  jz      short loc_180003576
0x180003556  test    byte ptr [rcx+1Ch], 2
0x18000355a  jz      short loc_180003576
0x18000355c  mov     rcx, [rcx+10h]
0x180003560  lea     edx, [rdi+21h]
0x180003563  lea     r9, aPisqueuefrozen; "pIsQueueFrozen"
0x18000356a  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180003571  call    WPP_SF_s
0x180003576  mov     eax, 80070057h
0x18000357b  jmp     loc_18000370D
0x180003580  mov     rcx, [rcx+40h]; lpFileName
0x180003584  cmp     dword ptr [rcx-10h], 0
0x180003588  jnz     short loc_1800035CE
0x18000358a  mov     r9d, 8000FFFFh
0x180003590  mov     ebx, r9d
0x180003593  mov     rcx, cs:WPP_GLOBAL_Control
0x18000359a  lea     rax, WPP_GLOBAL_Control
0x1800035a1  cmp     rcx, rax
0x1800035a4  jz      loc_18000370B
0x1800035aa  test    byte ptr [rcx+1Ch], 2
0x1800035ae  jz      loc_18000370B
0x1800035b4  mov     edx, 22h ; '"'
0x1800035b9  mov     rcx, [rcx+10h]
0x1800035bd  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x1800035c4  call    WPP_SF_d
0x1800035c9  jmp     loc_18000370B
0x1800035ce  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800035d7  mov     r8d, 3; dwShareMode
0x1800035dd  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800035e5  xor     r9d, r9d; lpSecurityAttributes
0x1800035e8  mov     edx, 80000000h; dwDesiredAccess
0x1800035ed  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800035f2  call    cs:__imp_CreateFileW
0x1800035f8  mov     rsi, rax
0x1800035fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800035ff  jnz     short loc_180003644
0x180003601  call    cs:__imp_GetLastError
0x180003607  mov     ebx, eax
0x180003609  test    eax, eax
0x18000360b  jle     short loc_180003616
0x18000360d  movzx   ebx, ax
0x180003610  or      ebx, 80070000h
0x180003616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000361d  lea     rax, WPP_GLOBAL_Control
0x180003624  cmp     rcx, rax
0x180003627  jz      loc_18000370B
0x18000362d  test    byte ptr [rcx+1Ch], 2
0x180003631  jz      loc_18000370B
0x180003637  mov     edx, 23h ; '#'
0x18000363c  mov     r9d, ebx
0x18000363f  jmp     loc_1800035B9
0x180003644  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000364d  lea     rax, [rsp+48h+BytesReturned]
0x180003652  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x180003657  xor     r9d, r9d; nInBufferSize
0x18000365a  lea     rax, [rsp+48h+OutBuffer]
0x18000365f  mov     [rsp+48h+dwFlagsAndAttributes], 1; nOutBufferSize
0x180003667  xor     r8d, r8d; lpInBuffer
0x18000366a  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; lpOutBuffer
0x18000366f  mov     edx, 2D141Ch; dwIoControlCode
0x180003674  mov     rcx, rsi; hDevice
0x180003677  call    cs:__imp_DeviceIoControl
0x18000367d  test    eax, eax
0x18000367f  jnz     short loc_1800036C9
0x180003681  call    cs:__imp_GetLastError
0x180003687  mov     ebx, eax
0x180003689  test    eax, eax
0x18000368b  jle     short loc_180003696
0x18000368d  movzx   ebx, ax
0x180003690  or      ebx, 80070000h
0x180003696  mov     rcx, cs:WPP_GLOBAL_Control
0x18000369d  lea     rax, WPP_GLOBAL_Control
0x1800036a4  cmp     rcx, rax
0x1800036a7  jz      short loc_180003702
0x1800036a9  test    byte ptr [rcx+1Ch], 2
0x1800036ad  jz      short loc_180003702
0x1800036af  mov     edx, 24h ; '$'
0x1800036b4  mov     r9d, ebx
0x1800036b7  mov     rcx, [rcx+10h]
0x1800036bb  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x1800036c2  call    WPP_SF_d
0x1800036c7  jmp     short loc_180003702
0x1800036c9  cmp     [rsp+48h+BytesReturned], 1
0x1800036ce  jz      short loc_1800036F9
0x1800036d0  mov     r9d, 8000FFFFh
0x1800036d6  mov     ebx, r9d
0x1800036d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036e0  lea     rax, WPP_GLOBAL_Control
0x1800036e7  cmp     rcx, rax
0x1800036ea  jz      short loc_180003702
0x1800036ec  test    byte ptr [rcx+1Ch], 2
0x1800036f0  jz      short loc_180003702
0x1800036f2  mov     edx, 25h ; '%'
0x1800036f7  jmp     short loc_1800036B7
0x1800036f9  movzx   ecx, [rsp+48h+OutBuffer]
0x1800036fe  xor     ebx, ebx
0x180003700  mov     [rdi], ecx
0x180003702  mov     rcx, rsi; hObject
0x180003705  call    cs:__imp_CloseHandle
0x18000370b  mov     eax, ebx
0x18000370d  mov     rbx, [rsp+48h+arg_0]
0x180003712  mov     rsi, [rsp+48h+arg_18]
0x180003717  add     rsp, 40h
0x18000371b  pop     rdi
0x18000371c  retn
```
