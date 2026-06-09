# LocalCredIsMarshaledCredentialW(ushort const *)

- ea: `0x180007fc4`
- end: `0x180008004`
- name: `?LocalCredIsMarshaledCredentialW@@YAHPEBG@Z`
- size: `64`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008a40`
- `0x1800092d0`
- `0x18000a070`

## callees

- `0x180004050`
- `0x180007fc4`
- `0x1800081c4`

## pseudocode

```c
__int64 __fastcall LocalCredIsMarshaledCredentialW(const unsigned __int16 *a1)
{
  int v2; // [rsp+38h] [rbp+10h] BYREF
  PVOID DataBuffer; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  DataBuffer = 0;
  if ( (unsigned int)LocalCredUnmarshalCredentialW(a1, (enum _CRED_MARSHAL_TYPE *)&v2, (char **)&DataBuffer) )
    return 0;
  SspiLocalFree(DataBuffer);
  return 1;
}

```

## disassembly

```asm
0x180007fc4  mov     rax, rsp
0x180007fc7  sub     rsp, 28h
0x180007fcb  lea     r8, [rax+18h]; void **
0x180007fcf  mov     dword ptr [rax+10h], 0
0x180007fd6  lea     rdx, [rax+10h]; enum _CRED_MARSHAL_TYPE *
0x180007fda  mov     qword ptr [rax+18h], 0
0x180007fe2  call    ?LocalCredUnmarshalCredentialW@@YAKPEBGPEAW4_CRED_MARSHAL_TYPE@@PEAPEAX@Z; LocalCredUnmarshalCredentialW(ushort const *,_CRED_MARSHAL_TYPE *,void * *)
0x180007fe7  test    eax, eax
0x180007fe9  jz      short loc_180007FEF
0x180007feb  xor     eax, eax
0x180007fed  jmp     short loc_180007FFE
0x180007fef  mov     rcx, [rsp+28h+DataBuffer]; DataBuffer
0x180007ff4  call    SspiLocalFree
0x180007ff9  mov     eax, 1
0x180007ffe  add     rsp, 28h
0x180008002  retn
```
