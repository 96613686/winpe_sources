# GenerateUniqueID(_GUID *)

- ea: `0x180009b1c`
- end: `0x180009b8a`
- name: `?GenerateUniqueID@@YAXPEAU_GUID@@@Z`
- size: `110`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004590`

## callees

- `0x180009b1c`
- `0x18001aac0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180009b34`
- `RPCRT4!UuidCreate` at `0x180009b34`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180009b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180009b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009b3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009b3e`

## pseudocode

```c
void __fastcall GenerateUniqueID(struct _GUID *a1)
{
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  if ( UuidCreate(a1) )
  {
    a1->Data1 = GetTickCount();
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    a1->Data2 = SystemTime.wMilliseconds;
    a1->Data3 = SystemTime.wSecond;
    *(_WORD *)&a1->Data4[4] = SystemTime.wMinute;
    *(_DWORD *)a1->Data4 = (_DWORD)a1;
  }
}

```

## disassembly

```asm
0x180009b1c  push    rbx
0x180009b1e  sub     rsp, 40h
0x180009b22  mov     rax, cs:__security_cookie
0x180009b29  xor     rax, rsp
0x180009b2c  mov     [rsp+48h+var_18], rax
0x180009b31  mov     rbx, rcx
0x180009b34  call    cs:__imp_UuidCreate
0x180009b3a  test    eax, eax
0x180009b3c  jz      short loc_180009B77
0x180009b3e  call    cs:__imp_GetTickCount
0x180009b44  xorps   xmm0, xmm0
0x180009b47  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180009b4c  mov     [rbx], eax
0x180009b4e  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x180009b53  call    cs:__imp_GetSystemTime
0x180009b59  movzx   eax, [rsp+48h+SystemTime.wMilliseconds]
0x180009b5e  mov     [rbx+4], ax
0x180009b62  movzx   eax, [rsp+48h+SystemTime.wSecond]
0x180009b67  mov     [rbx+6], ax
0x180009b6b  movzx   eax, [rsp+48h+SystemTime.wMinute]
0x180009b70  mov     [rbx+0Ch], ax
0x180009b74  mov     [rbx+8], ebx
0x180009b77  mov     rcx, [rsp+48h+var_18]
0x180009b7c  xor     rcx, rsp; StackCookie
0x180009b7f  call    __security_check_cookie
0x180009b84  add     rsp, 40h
0x180009b88  pop     rbx
0x180009b89  retn
```
