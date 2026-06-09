# SetFileListIntegrityLevel(sFNAME *,int)

- ea: `0x14000b334`
- end: `0x14000b3b8`
- name: `?SetFileListIntegrityLevel@@YAJPEAUsFNAME@@H@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct sFNAME *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004738`
- `0x1400048c0`

## callees

- `0x14000a4b0`
- `0x14000b150`
- `0x14000b248`
- `0x14000b334`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000b391`
- `ole32!CoTaskMemFree` at `0x14000b391`

## pseudocode

```c
__int64 __fastcall SetFileListIntegrityLevel(struct sFNAME *a1)
{
  int v1; // edi
  struct sFNAME *v2; // rbx
  const char *v3; // rdx
  int v4; // eax
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v2 = a1;
  while ( v2 )
  {
    v3 = *(const char **)v2;
    if ( *(_QWORD *)v2 )
    {
      pv = 0;
      v1 = SZtoWSZ((__int64)a1, v3, (unsigned __int16 **)&pv);
      if ( v1 < 0 )
        return (unsigned int)v1;
      v4 = IsFileAtIntegrityLevel((const unsigned __int16 *)pv);
      if ( v4 == 1 )
        v4 = SetFileIntegrityLevelByNameW((const unsigned __int16 *)pv);
      v1 = 0;
      if ( v4 != -2147024894 )
        v1 = v4;
      CoTaskMemFree(pv);
      if ( v1 < 0 )
        return (unsigned int)v1;
      v2 = (struct sFNAME *)*((_QWORD *)v2 + 1);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000b334  mov     [rsp+arg_8], rbx
0x14000b339  push    rdi
0x14000b33a  sub     rsp, 20h
0x14000b33e  xor     edi, edi
0x14000b340  mov     rbx, rcx
0x14000b343  test    rcx, rcx
0x14000b346  jz      short loc_14000B3AA
0x14000b348  mov     rdx, [rbx]; char *
0x14000b34b  test    rdx, rdx
0x14000b34e  jz      short loc_14000B3A5
0x14000b350  lea     r8, [rsp+28h+pv]; unsigned __int16 **
0x14000b355  mov     [rsp+28h+pv], 0
0x14000b35e  call    ?SZtoWSZ@@YAJIPEBDPEAPEAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x14000b363  mov     edi, eax
0x14000b365  test    eax, eax
0x14000b367  js      short loc_14000B3AA
0x14000b369  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x14000b36e  call    ?IsFileAtIntegrityLevel@@YAJPEBGH@Z; IsFileAtIntegrityLevel(ushort const *,int)
0x14000b373  cmp     eax, 1
0x14000b376  jnz     short loc_14000B382
0x14000b378  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x14000b37d  call    ?SetFileIntegrityLevelByNameW@@YAJPEBGH@Z; SetFileIntegrityLevelByNameW(ushort const *,int)
0x14000b382  mov     rcx, [rsp+28h+pv]; pv
0x14000b387  xor     edi, edi
0x14000b389  cmp     eax, 80070002h
0x14000b38e  cmovnz  edi, eax
0x14000b391  call    cs:__imp_CoTaskMemFree
0x14000b398  nop     dword ptr [rax+rax+00h]
0x14000b39d  test    edi, edi
0x14000b39f  js      short loc_14000B3AA
0x14000b3a1  mov     rbx, [rbx+8]
0x14000b3a5  test    rbx, rbx
0x14000b3a8  jnz     short loc_14000B348
0x14000b3aa  mov     rbx, [rsp+28h+arg_8]
0x14000b3af  mov     eax, edi
0x14000b3b1  add     rsp, 20h
0x14000b3b5  pop     rdi
0x14000b3b6  retn
```
