# TextLogGetLogStatus

- ea: `0x180005018`
- end: `0x1800050af`
- name: `TextLogGetLogStatus`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800052c4`
- `0x1800063bc`
- `0x180006590`

## callees

- `0x180003820`
- `0x180003988`
- `0x180005018`
- `0x180006fb0`

## import_xrefs

- `ntdll!NtClose` at `0x18000509c`
- `ntdll!NtClose` at `0x18000509c`

## pseudocode

```c
__int64 __fastcall TextLogGetLogStatus(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v5; // rcx
  const WCHAR *FileTitle; // rax
  HANDLE Handle[3]; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v10 = 0;
  Handle[0] = 0;
  v9 = 0;
  if ( !(unsigned int)pSetupOpenKey((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogStatus", a3, 1u, Handle) )
  {
    v5 = *(_QWORD *)(a1 + 16);
    LODWORD(v11) = 4;
    FileTitle = (const WCHAR *)pSetupGetFileTitle(v5);
    if ( !(unsigned int)pSetupQueryValue(Handle[0], FileTitle, &v9, &v10, (unsigned int *)&v11) && v9 == 4 )
      v3 = v10;
    NtClose((HANDLE)LODWORD(Handle[0]));
  }
  return v3;
}

```

## disassembly

```asm
0x180005018  mov     rax, rsp
0x18000501b  mov     [rax+8], rbx
0x18000501f  push    rdi
0x180005020  sub     rsp, 40h
0x180005024  xor     ebx, ebx
0x180005026  mov     rdi, rcx
0x180005029  mov     [rax+18h], ebx
0x18000502c  lea     rdx, aSystemSetupSet_0; "SYSTEM\\Setup\\SetupapiLogStatus"
0x180005033  mov     [rax-18h], rbx
0x180005037  mov     rcx, 0FFFFFFFF80000002h
0x18000503e  mov     [rax+10h], ebx
0x180005041  lea     rax, [rax-18h]
0x180005045  lea     r9d, [rbx+1]
0x180005049  mov     [rsp+48h+var_28], rax
0x18000504e  call    pSetupOpenKey
0x180005053  test    eax, eax
0x180005055  jnz     short loc_1800050A2
0x180005057  mov     rcx, [rdi+10h]
0x18000505b  mov     dword ptr [rsp+48h+arg_18], 4
0x180005063  call    pSetupGetFileTitle
0x180005068  mov     rcx, [rsp+48h+Handle]; KeyHandle
0x18000506d  lea     r9, [rsp+48h+arg_10]
0x180005072  mov     rdx, rax; SourceString
0x180005075  lea     r8, [rsp+48h+arg_8]
0x18000507a  lea     rax, [rsp+48h+arg_18]
0x18000507f  mov     [rsp+48h+var_28], rax; __int64
0x180005084  call    pSetupQueryValue
0x180005089  test    eax, eax
0x18000508b  jnz     short loc_180005098
0x18000508d  cmp     [rsp+48h+arg_8], 4
0x180005092  jnz     short loc_180005098
0x180005094  mov     ebx, [rsp+48h+arg_10]
0x180005098  mov     ecx, dword ptr [rsp+48h+Handle]; Handle
0x18000509c  call    cs:__imp_NtClose
0x1800050a2  mov     eax, ebx
0x1800050a4  mov     rbx, [rsp+48h+arg_0]
0x1800050a9  add     rsp, 40h
0x1800050ad  pop     rdi
0x1800050ae  retn
```
