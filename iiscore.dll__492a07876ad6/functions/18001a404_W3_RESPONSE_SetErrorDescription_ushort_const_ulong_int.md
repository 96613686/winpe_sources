# W3_RESPONSE::SetErrorDescription(ushort const *,ulong,int)

- ea: `0x18001a404`
- end: `0x18001a4aa`
- name: `?SetErrorDescription@W3_RESPONSE@@QEAAJPEBGKH@Z`
- size: `166`
- prototype: `int(W3_RESPONSE *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006060`
- `0x180006f10`
- `0x18000c780`
- `0x180024300`
- `0x180030738`

## callees

- `0x180009030`
- `0x18001a404`
- `0x180027d78`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001a479`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001a479`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x18001a494`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x18001a494`

## pseudocode

```c
int __fastcall W3_RESPONSE::SetErrorDescription(W3_RESPONSE *this, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  int result; // eax
  __int64 v9; // rcx

  if ( !a2 )
    return -2147024809;
  v9 = *((_QWORD *)this + 6);
  if ( *(_BYTE *)(v9 + 9098)
    && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v9 + 8) & -(__int64)(v9 != 0), 256, 3) )
  {
    IISRequestNotificationEvents::SET_RESPONSE_ERROR_DESCRIPTION::RaiseEvent(
      (struct IHttpTraceContext *)((*((_QWORD *)this + 6) + 8LL) & -(__int64)(*((_QWORD *)this + 6) != 0)),
      (const struct _GUID *)(*((_QWORD *)this + 6) + 8LL),
      a2);
  }
  result = STRU::Copy((W3_RESPONSE *)((char *)this + 656), a2, a3);
  if ( result >= 0 )
  {
    if ( a4 )
      return STRU::HTMLEncode((W3_RESPONSE *)((char *)this + 656));
  }
  return result;
}

```

## disassembly

```asm
0x18001a404  push    rbx
0x18001a406  push    rbp
0x18001a407  push    rsi
0x18001a408  push    rdi
0x18001a409  sub     rsp, 28h
0x18001a40d  mov     esi, r9d
0x18001a410  mov     ebp, r8d
0x18001a413  mov     rdi, rdx
0x18001a416  mov     rbx, rcx
0x18001a419  test    rdx, rdx
0x18001a41c  jnz     short loc_18001A425
0x18001a41e  mov     eax, 80070057h
0x18001a423  jmp     short loc_18001A4A0
0x18001a425  mov     rcx, [rcx+30h]
0x18001a429  cmp     byte ptr [rcx+238Ah], 0
0x18001a430  jz      short loc_18001A46C
0x18001a432  lea     rax, [rcx+8]
0x18001a436  mov     edx, 100h
0x18001a43b  neg     rcx
0x18001a43e  mov     r8d, 3
0x18001a444  sbb     rcx, rcx
0x18001a447  and     rcx, rax
0x18001a44a  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18001a44f  test    eax, eax
0x18001a451  jz      short loc_18001A46C
0x18001a453  mov     rax, [rbx+30h]
0x18001a457  mov     r8, rdi; unsigned __int16 *
0x18001a45a  lea     rdx, [rax+8]; struct _GUID *
0x18001a45e  neg     rax
0x18001a461  sbb     rcx, rcx
0x18001a464  and     rcx, rdx; struct IHttpTraceContext *
0x18001a467  call    ?RaiseEvent@SET_RESPONSE_ERROR_DESCRIPTION@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISRequestNotificationEvents::SET_RESPONSE_ERROR_DESCRIPTION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x18001a46c  mov     r8d, ebp
0x18001a46f  lea     rcx, [rbx+290h]
0x18001a476  mov     rdx, rdi
0x18001a479  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001a480  nop     dword ptr [rax+rax+00h]
0x18001a485  test    eax, eax
0x18001a487  js      short loc_18001A4A0
0x18001a489  test    esi, esi
0x18001a48b  jz      short loc_18001A4A0
0x18001a48d  lea     rcx, [rbx+290h]
0x18001a494  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x18001a49b  nop     dword ptr [rax+rax+00h]
0x18001a4a0  add     rsp, 28h
0x18001a4a4  pop     rdi
0x18001a4a5  pop     rsi
0x18001a4a6  pop     rbp
0x18001a4a7  pop     rbx
0x18001a4a8  retn
```
