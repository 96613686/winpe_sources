# HSTS_HANDLER::CheckRequestHttps(IHttpContext *,int *)

- ea: `0x1800040c8`
- end: `0x180004135`
- name: `?CheckRequestHttps@HSTS_HANDLER@@CAJPEAVIHttpContext@@PEAH@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001580`

## callees

- `0x1800040c8`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall HSTS_HANDLER::CheckRequestHttps(struct IHttpContext *a1, int *a2)
{
  __int64 v2; // rax
  __int64 result; // rax
  int v5; // edx
  int v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 *v7; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a1;
  v7 = 0;
  v6 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, unsigned __int8 **, int *))(v2 + 120))(
             a1,
             "HTTPS",
             &v7,
             &v6);
  if ( (int)result >= 0 )
  {
    v5 = *v7 - 111;
    if ( *v7 == 111 )
    {
      v5 = v7[1] - 110;
      if ( v7[1] == 110 )
        v5 = v7[2];
    }
    *a2 = v5 == 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800040c8  push    rbx
0x1800040ca  sub     rsp, 30h
0x1800040ce  mov     rax, [rcx]
0x1800040d1  lea     r9, [rsp+38h+arg_0]
0x1800040d6  mov     rbx, rdx
0x1800040d9  mov     [rsp+38h+arg_10], 0
0x1800040e2  lea     r8, [rsp+38h+arg_10]
0x1800040e7  mov     [rsp+38h+arg_0], 0
0x1800040ef  lea     rdx, aHttps_0; "HTTPS"
0x1800040f6  mov     rax, [rax+78h]
0x1800040fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ff  test    eax, eax
0x180004101  js      short loc_18000412F
0x180004103  mov     rcx, [rsp+38h+arg_10]
0x180004108  movzx   edx, byte ptr [rcx]
0x18000410b  sub     edx, 6Fh ; 'o'
0x18000410e  jnz     short loc_180004124
0x180004110  movzx   edx, byte ptr [rcx+1]
0x180004114  sub     edx, 6Eh ; 'n'
0x180004117  jnz     short loc_180004124
0x180004119  movzx   edx, byte ptr [rcx+2]
0x18000411d  xor     eax, eax
0x18000411f  movzx   ecx, al
0x180004122  sub     edx, ecx
0x180004124  xor     eax, eax
0x180004126  test    edx, edx
0x180004128  setz    al
0x18000412b  mov     [rbx], eax
0x18000412d  xor     eax, eax
0x18000412f  add     rsp, 30h
0x180004133  pop     rbx
0x180004134  retn
```
