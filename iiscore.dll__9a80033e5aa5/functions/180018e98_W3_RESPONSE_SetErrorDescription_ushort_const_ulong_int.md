# W3_RESPONSE::SetErrorDescription(ushort const *,ulong,int)

- ea: `0x180018e98`
- end: `0x180018f31`
- name: `?SetErrorDescription@W3_RESPONSE@@QEAAJPEBGKH@Z`
- size: `153`
- prototype: `int(W3_RESPONSE *__hidden this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005bf0`
- `0x180006a70`
- `0x18000b920`
- `0x180022670`
- `0x18002dcb8`

## callees

- `0x180008930`
- `0x180018e98`
- `0x180025d94`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180018f0d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180018f0d`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180018f22`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x180018f22`

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
0x180018e98  push    rbx
0x180018e9a  push    rbp
0x180018e9b  push    rsi
0x180018e9c  push    rdi
0x180018e9d  sub     rsp, 28h
0x180018ea1  mov     esi, r9d
0x180018ea4  mov     ebp, r8d
0x180018ea7  mov     rdi, rdx
0x180018eaa  mov     rbx, rcx
0x180018ead  test    rdx, rdx
0x180018eb0  jnz     short loc_180018EB9
0x180018eb2  mov     eax, 80070057h
0x180018eb7  jmp     short loc_180018F28
0x180018eb9  mov     rcx, [rcx+30h]
0x180018ebd  cmp     byte ptr [rcx+238Ah], 0
0x180018ec4  jz      short loc_180018F00
0x180018ec6  lea     rax, [rcx+8]
0x180018eca  mov     edx, 100h
0x180018ecf  neg     rcx
0x180018ed2  mov     r8d, 3
0x180018ed8  sbb     rcx, rcx
0x180018edb  and     rcx, rax
0x180018ede  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180018ee3  test    eax, eax
0x180018ee5  jz      short loc_180018F00
0x180018ee7  mov     rax, [rbx+30h]
0x180018eeb  mov     r8, rdi; unsigned __int16 *
0x180018eee  lea     rdx, [rax+8]; struct _GUID *
0x180018ef2  neg     rax
0x180018ef5  sbb     rcx, rcx
0x180018ef8  and     rcx, rdx; struct IHttpTraceContext *
0x180018efb  call    ?RaiseEvent@SET_RESPONSE_ERROR_DESCRIPTION@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG@Z; IISRequestNotificationEvents::SET_RESPONSE_ERROR_DESCRIPTION::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *)
0x180018f00  mov     r8d, ebp
0x180018f03  lea     rcx, [rbx+290h]
0x180018f0a  mov     rdx, rdi
0x180018f0d  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180018f13  test    eax, eax
0x180018f15  js      short loc_180018F28
0x180018f17  test    esi, esi
0x180018f19  jz      short loc_180018F28
0x180018f1b  lea     rcx, [rbx+290h]
0x180018f22  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x180018f28  add     rsp, 28h
0x180018f2c  pop     rdi
0x180018f2d  pop     rsi
0x180018f2e  pop     rbp
0x180018f2f  pop     rbx
0x180018f30  retn
```
