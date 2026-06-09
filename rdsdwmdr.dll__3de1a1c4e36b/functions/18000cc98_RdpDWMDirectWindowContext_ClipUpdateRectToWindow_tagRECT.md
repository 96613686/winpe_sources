# RdpDWMDirectWindowContext::ClipUpdateRectToWindow(tagRECT *)

- ea: `0x18000cc98`
- end: `0x18000cde0`
- name: `?ClipUpdateRectToWindow@RdpDWMDirectWindowContext@@IEAAHPEAUtagRECT@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, struct tagRECT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000cf04`
- `0x18000ea10`

## callees

- `0x180002a04`
- `0x18000cc98`
- `0x18002b960`

## import_xrefs

- `USER32!IntersectRect` at `0x18000cdb4`
- `USER32!IntersectRect` at `0x18000cdb4`
- `USER32!EqualRect` at `0x18000cd03`
- `USER32!EqualRect` at `0x18000cd03`
- `USER32!UnionRect` at `0x18000ccf5`
- `USER32!UnionRect` at `0x18000ccf5`
- `USER32!SetRect` at `0x18000cce4`
- `USER32!SetRect` at `0x18000cce4`

## string_xrefs

- `0x18000cd52`: `Clipping update rect that is outside the bounds for window`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::ClipUpdateRectToWindow(
        RdpDWMDirectWindowContext *this,
        struct tagRECT *a2)
{
  int v3; // r9d
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int yBottom; // [rsp+20h] [rbp-49h]
  int v11; // [rsp+60h] [rbp-9h] BYREF
  int v12; // [rsp+64h] [rbp-5h] BYREF
  LONG bottom; // [rsp+68h] [rbp-1h] BYREF
  LONG right; // [rsp+6Ch] [rbp+3h] BYREF
  LONG top; // [rsp+70h] [rbp+7h] BYREF
  LONG left; // [rsp+74h] [rbp+Bh] BYREF
  __int64 v17; // [rsp+78h] [rbp+Fh] BYREF
  const char *v18; // [rsp+80h] [rbp+17h] BYREF
  struct tagRECT rc; // [rsp+88h] [rbp+1Fh] BYREF
  struct tagRECT rcDst; // [rsp+98h] [rbp+2Fh] BYREF

  v3 = *((_DWORD *)this + 22);
  yBottom = *((_DWORD *)this + 23);
  rc = 0;
  v5 = 0;
  rcDst = 0;
  SetRect(&rc, 0, 0, v3, yBottom);
  UnionRect(&rcDst, &rc, a2);
  if ( !EqualRect(&rc, &rcDst) )
  {
    if ( (unsigned int)dword_180044008 > 3 )
    {
      v11 = *((_DWORD *)this + 23);
      v12 = *((_DWORD *)this + 22);
      bottom = a2->bottom;
      right = a2->right;
      top = a2->top;
      left = a2->left;
      v17 = *((_QWORD *)this + 8);
      v18 = "Clipping update rect that is outside the bounds for window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)qword_180038C10,
        v7,
        v8,
        (const unsigned __int16 **)&v18,
        (__int64)&v17,
        (__int64)&left,
        (__int64)&top,
        (__int64)&right,
        (__int64)&bottom,
        (__int64)&v12,
        (__int64)&v11);
    }
    IntersectRect(a2, a2, &rc);
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x18000cc98  mov     [rsp-8+arg_10], rbx
0x18000cc9d  push    rbp
0x18000cc9e  push    rsi
0x18000cc9f  push    rdi
0x18000cca0  lea     rbp, [rsp-47h]
0x18000cca5  sub     rsp, 0B0h
0x18000ccac  mov     rax, cs:__security_cookie
0x18000ccb3  xor     rax, rsp
0x18000ccb6  mov     [rbp+57h+var_18], rax
0x18000ccba  mov     eax, [rcx+5Ch]
0x18000ccbd  mov     rbx, rdx
0x18000ccc0  mov     r9d, [rcx+58h]; xRight
0x18000ccc4  mov     rsi, rcx
0x18000ccc7  xorps   xmm0, xmm0
0x18000ccca  mov     [rsp+0C0h+yBottom], eax; yBottom
0x18000ccce  xorps   xmm1, xmm1
0x18000ccd1  lea     rcx, [rbp+57h+rc]; lprc
0x18000ccd5  xor     edx, edx; xLeft
0x18000ccd7  xor     r8d, r8d; yTop
0x18000ccda  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000ccde  xor     edi, edi
0x18000cce0  movups  xmmword ptr [rbp+57h+rcDst.left], xmm1
0x18000cce4  call    cs:__imp_SetRect
0x18000ccea  mov     r8, rbx; lprcSrc2
0x18000cced  lea     rdx, [rbp+57h+rc]; lprcSrc1
0x18000ccf1  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18000ccf5  call    cs:__imp_UnionRect
0x18000ccfb  lea     rdx, [rbp+57h+rcDst]; lprc2
0x18000ccff  lea     rcx, [rbp+57h+rc]; lprc1
0x18000cd03  call    cs:__imp_EqualRect
0x18000cd09  test    eax, eax
0x18000cd0b  jnz     loc_18000CDBF
0x18000cd11  mov     eax, cs:dword_180044008
0x18000cd17  cmp     eax, 3
0x18000cd1a  jbe     loc_18000CDAA
0x18000cd20  mov     eax, [rsi+5Ch]
0x18000cd23  lea     rdx, qword_180038C10
0x18000cd2a  mov     [rbp+57h+var_60], eax
0x18000cd2d  mov     eax, [rsi+58h]
0x18000cd30  mov     [rbp+57h+var_5C], eax
0x18000cd33  mov     eax, [rbx+0Ch]
0x18000cd36  mov     [rbp+57h+var_58], eax
0x18000cd39  mov     eax, [rbx+8]
0x18000cd3c  mov     [rbp+57h+var_54], eax
0x18000cd3f  mov     eax, [rbx+4]
0x18000cd42  mov     [rbp+57h+var_50], eax
0x18000cd45  mov     eax, [rbx]
0x18000cd47  mov     [rbp+57h+var_4C], eax
0x18000cd4a  mov     rax, [rsi+40h]
0x18000cd4e  mov     [rbp+57h+var_48], rax
0x18000cd52  lea     rax, aClippingUpdate; "Clipping update rect that is outside th"...
0x18000cd59  mov     [rbp+57h+var_40], rax
0x18000cd5d  lea     rax, [rbp+57h+var_60]
0x18000cd61  mov     [rsp+0C0h+var_68], rax
0x18000cd66  lea     rax, [rbp+57h+var_5C]
0x18000cd6a  mov     [rsp+0C0h+var_70], rax
0x18000cd6f  lea     rax, [rbp+57h+var_58]
0x18000cd73  mov     [rsp+0C0h+var_78], rax
0x18000cd78  lea     rax, [rbp+57h+var_54]
0x18000cd7c  mov     [rsp+0C0h+var_80], rax
0x18000cd81  lea     rax, [rbp+57h+var_50]
0x18000cd85  mov     [rsp+0C0h+var_88], rax
0x18000cd8a  lea     rax, [rbp+57h+var_4C]
0x18000cd8e  mov     [rsp+0C0h+var_90], rax
0x18000cd93  lea     rax, [rbp+57h+var_48]
0x18000cd97  mov     [rsp+0C0h+var_98], rax
0x18000cd9c  lea     rax, [rbp+57h+var_40]
0x18000cda0  mov     qword ptr [rsp+0C0h+yBottom], rax
0x18000cda5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cdaa  lea     r8, [rbp+57h+rc]; lprcSrc2
0x18000cdae  mov     rdx, rbx; lprcSrc1
0x18000cdb1  mov     rcx, rbx; lprcDst
0x18000cdb4  call    cs:__imp_IntersectRect
0x18000cdba  mov     edi, 1
0x18000cdbf  mov     eax, edi
0x18000cdc1  mov     rcx, [rbp+57h+var_18]
0x18000cdc5  xor     rcx, rsp; StackCookie
0x18000cdc8  call    __security_check_cookie
0x18000cdcd  mov     rbx, [rsp+0C0h+arg_10]
0x18000cdd5  add     rsp, 0B0h
0x18000cddc  pop     rdi
0x18000cddd  pop     rsi
0x18000cdde  pop     rbp
0x18000cddf  retn
```
