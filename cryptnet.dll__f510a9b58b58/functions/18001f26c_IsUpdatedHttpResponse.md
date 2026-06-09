# _IsUpdatedHttpResponse

- ea: `0x18001f26c`
- end: `0x18001f307`
- name: `_IsUpdatedHttpResponse`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001f61c`

## callees

- `0x180003274`
- `0x18000a990`
- `0x18001f26c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f2ac`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001f2ac`

## pseudocode

```c
__int64 __fastcall IsUpdatedHttpResponse(__int64 a1)
{
  unsigned int v2; // edi
  const FILETIME *v3; // rax
  FILETIME *v4; // rsi
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // edx
  unsigned __int16 *v12; // [rsp+30h] [rbp+8h] BYREF

  v12 = 0;
  v2 = 1;
  v3 = (const FILETIME *)SchemeRetrieveCacheMetaData(*(_QWORD *)(a1 + 88), &v12, 0);
  v4 = (FILETIME *)v3;
  if ( v3 && !CompareFileTime((const FILETIME *)(a1 + 104), v3 + 11) )
  {
    v5 = v12;
    v6 = *(_QWORD *)(a1 + 112);
    if ( v12 )
    {
      if ( !v6 )
        goto LABEL_12;
      v8 = v6 - (_QWORD)v12;
      do
      {
        v9 = *(unsigned __int16 *)((char *)v5 + v8);
        v10 = *v5 - v9;
        if ( v10 )
          break;
        ++v5;
      }
      while ( v9 );
      v7 = v10 == 0;
    }
    else
    {
      v7 = v6 == 0;
    }
    if ( v7 )
      v2 = 0;
  }
LABEL_12:
  operator delete(v4);
  return v2;
}

```

## disassembly

```asm
0x18001f26c  mov     rax, rsp
0x18001f26f  mov     [rax+10h], rbx
0x18001f273  mov     [rax+18h], rsi
0x18001f277  push    rdi
0x18001f278  sub     rsp, 20h
0x18001f27c  mov     rbx, rcx
0x18001f27f  mov     qword ptr [rax+8], 0
0x18001f287  mov     rcx, [rcx+58h]
0x18001f28b  lea     rdx, [rax+8]
0x18001f28f  xor     r8d, r8d
0x18001f292  mov     edi, 1
0x18001f297  call    SchemeRetrieveCacheMetaData
0x18001f29c  mov     rsi, rax
0x18001f29f  test    rax, rax
0x18001f2a2  jz      short loc_18001F2ED
0x18001f2a4  lea     rdx, [rax+58h]; lpFileTime2
0x18001f2a8  lea     rcx, [rbx+68h]; lpFileTime1
0x18001f2ac  call    cs:__imp_CompareFileTime
0x18001f2b2  test    eax, eax
0x18001f2b4  jnz     short loc_18001F2ED
0x18001f2b6  mov     rax, [rsp+28h+arg_0]
0x18001f2bb  mov     rcx, [rbx+70h]
0x18001f2bf  test    rax, rax
0x18001f2c2  jnz     short loc_18001F2C9
0x18001f2c4  test    rcx, rcx
0x18001f2c7  jmp     short loc_18001F2E9
0x18001f2c9  test    rcx, rcx
0x18001f2cc  jz      short loc_18001F2ED
0x18001f2ce  sub     rcx, rax
0x18001f2d1  movzx   edx, word ptr [rax]
0x18001f2d4  movzx   r8d, word ptr [rax+rcx]
0x18001f2d9  sub     edx, r8d
0x18001f2dc  jnz     short loc_18001F2E7
0x18001f2de  add     rax, 2
0x18001f2e2  test    r8d, r8d
0x18001f2e5  jnz     short loc_18001F2D1
0x18001f2e7  test    edx, edx
0x18001f2e9  jnz     short loc_18001F2ED
0x18001f2eb  xor     edi, edi
0x18001f2ed  mov     rcx, rsi; hMem
0x18001f2f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f2f5  mov     rbx, [rsp+28h+arg_8]
0x18001f2fa  mov     eax, edi
0x18001f2fc  mov     rsi, [rsp+28h+arg_10]
0x18001f301  add     rsp, 20h
0x18001f305  pop     rdi
0x18001f306  retn
```
