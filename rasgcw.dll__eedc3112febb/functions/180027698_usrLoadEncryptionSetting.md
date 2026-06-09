# usrLoadEncryptionSetting

- ea: `0x180027698`
- end: `0x180027728`
- name: `usrLoadEncryptionSetting`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002439c`
- `0x180024c4c`

## callees

- `0x180021720`
- `0x180027698`

## import_xrefs

- `MPRAPI!MprAdminUserReadProfFlags` at `0x1800276bc`
- `MPRAPI!MprAdminUserReadProfFlags` at `0x1800276bc`

## string_xrefs

- `0x1800276d1`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall usrLoadEncryptionSetting(__int64 *a1)
{
  __int64 v2; // rcx
  char v3; // di
  int v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  if ( !*((_DWORD *)a1 + 7) )
  {
    v2 = *a1;
    v3 = 2;
    v6 = 2;
    MprAdminUserReadProfFlags(v2, &v6);
    v5 = 0;
    RassrvRegGetDwEx(&v5, 0, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", L"ServerFlags");
    if ( (v5 & 0x800000) != 0 )
    {
      if ( (v5 & 0x38000) != 0 )
      {
        if ( (v5 & 0x38000) == 0x10000 )
          v3 = 0;
      }
      else
      {
        v3 = 1;
      }
    }
    *((_DWORD *)a1 + 4) = ((unsigned __int8)v3 & (unsigned __int8)v6 & 1) != 0;
    *((_DWORD *)a1 + 7) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180027698  mov     [rsp+arg_10], rbx
0x18002769d  push    rdi
0x18002769e  sub     rsp, 30h
0x1800276a2  cmp     dword ptr [rcx+1Ch], 0
0x1800276a6  mov     rbx, rcx
0x1800276a9  jnz     short loc_18002771B
0x1800276ab  mov     rcx, [rcx]
0x1800276ae  lea     rdx, [rsp+38h+arg_8]
0x1800276b3  mov     edi, 2
0x1800276b8  mov     [rsp+38h+arg_8], edi
0x1800276bc  call    cs:__imp_MprAdminUserReadProfFlags
0x1800276c2  lea     r9, pszregServerFlags; "ServerFlags"
0x1800276c9  mov     [rsp+38h+arg_0], 0
0x1800276d1  lea     r8, pszregRasParameters; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800276d8  xor     edx, edx
0x1800276da  lea     rcx, [rsp+38h+arg_0]
0x1800276df  call    RassrvRegGetDwEx
0x1800276e4  mov     eax, [rsp+38h+arg_0]
0x1800276e8  lea     ecx, [rdi-1]
0x1800276eb  bt      eax, 17h
0x1800276ef  jnb     short loc_180027705
0x1800276f1  and     eax, 38000h
0x1800276f6  jnz     short loc_1800276FC
0x1800276f8  mov     edi, ecx
0x1800276fa  jmp     short loc_180027705
0x1800276fc  cmp     eax, 10000h
0x180027701  jnz     short loc_180027705
0x180027703  xor     edi, edi
0x180027705  mov     eax, [rsp+38h+arg_8]
0x180027709  and     eax, edi
0x18002770b  test    cl, al
0x18002770d  mov     eax, 0
0x180027712  setnz   al
0x180027715  mov     [rbx+10h], eax
0x180027718  mov     [rbx+1Ch], ecx
0x18002771b  mov     rbx, [rsp+38h+arg_10]
0x180027720  xor     eax, eax
0x180027722  add     rsp, 30h
0x180027726  pop     rdi
0x180027727  retn
```
