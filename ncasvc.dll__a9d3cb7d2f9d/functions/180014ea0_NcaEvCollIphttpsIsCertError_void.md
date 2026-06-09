# NcaEvCollIphttpsIsCertError(void)

- ea: `0x180014ea0`
- end: `0x180014f32`
- name: `?NcaEvCollIphttpsIsCertError@@YAHXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014b80`
- `0x180014e00`

## callees

- `0x180004f34`
- `0x180014ea0`
- `0x18001a654`

## string_xrefs

- `0x180014ecc`: `SYSTEM\CurrentControlSet\Services\iphlpsvc\Parameters\IPHTTPS\IPHTTPSInterface`

## pseudocode

```c
__int64 NcaEvCollIphttpsIsCertError(void)
{
  int DWord; // eax
  unsigned int v1; // ebx
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = 0;
  LODWORD(v3) = 0;
  DWord = NcaRegQueryDWord(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\iphlpsvc\\Parameters\\IPHTTPS\\IPHTTPSInterface",
            L"ErrorCode",
            (LPBYTE)&Data,
            (__int64)&v3);
  v1 = 1;
  if ( DWord < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids,
      (unsigned int)DWord);
  if ( !(_DWORD)v3 || Data != 403 )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x180014ea0  push    rbx
0x180014ea2  sub     rsp, 30h
0x180014ea6  lea     rax, [rsp+38h+arg_0]
0x180014eab  mov     [rsp+38h+Data], 0
0x180014eb3  lea     r9, [rsp+38h+Data]; lpData
0x180014eb8  mov     [rsp+38h+var_18], rax; __int64
0x180014ebd  lea     r8, aErrorcode; "ErrorCode"
0x180014ec4  mov     dword ptr [rsp+38h+arg_0], 0
0x180014ecc  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\ip"...
0x180014ed3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014eda  call    NcaRegQueryDWord
0x180014edf  mov     ebx, 1
0x180014ee4  test    eax, eax
0x180014ee6  jns     short loc_180014F16
0x180014ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180014eef  lea     rdx, WPP_GLOBAL_Control
0x180014ef6  cmp     rcx, rdx
0x180014ef9  jz      short loc_180014F16
0x180014efb  test    [rcx+1Ch], bl
0x180014efe  jz      short loc_180014F16
0x180014f00  mov     rcx, [rcx+10h]
0x180014f04  lea     edx, [rbx+9]
0x180014f07  mov     r9d, eax
0x180014f0a  lea     r8, WPP_8db24c4892c836aea10a5a876d8eb362_Traceguids
0x180014f11  call    WPP_SF_d
0x180014f16  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014f1b  jz      short loc_180014F27
0x180014f1d  cmp     [rsp+38h+Data], 193h
0x180014f25  jz      short loc_180014F29
0x180014f27  xor     ebx, ebx
0x180014f29  mov     eax, ebx
0x180014f2b  add     rsp, 30h
0x180014f2f  pop     rbx
0x180014f30  retn
```
