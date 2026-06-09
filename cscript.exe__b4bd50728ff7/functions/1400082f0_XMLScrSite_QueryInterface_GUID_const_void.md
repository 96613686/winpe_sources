# XMLScrSite::QueryInterface(_GUID const &,void * *)

- ea: `0x1400082f0`
- end: `0x1400083b8`
- name: `?QueryInterface@XMLScrSite@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400118d0`
- `0x1400118e0`

## callees

- `0x1400082f0`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::QueryInterface(XMLScrSite *this, const struct _GUID *a2, XMLScrSite **a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  XMLScrSite *v10; // rdx

  if ( !a3 )
    return 2147500035LL;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v5 )
    goto LABEL_19;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IScriptletSite.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSite.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IScriptletSite.Data4;
  if ( v6 )
  {
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IScriptletSitePoll.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSitePoll.Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IScriptletSitePoll.Data4;
    if ( v7 )
    {
      v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IScriptletSiteWSH.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IScriptletSiteWSH.Data1 )
        v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IScriptletSiteWSH.Data4;
      if ( v9 )
      {
        *a3 = 0;
        return 2147500034LL;
      }
      v8 = (unsigned __int64)this + 16;
    }
    else
    {
      v8 = (unsigned __int64)this + 8;
    }
    v10 = (XMLScrSite *)(v8 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  }
  else
  {
LABEL_19:
    v10 = this;
  }
  *a3 = v10;
  (*(void (__fastcall **)(XMLScrSite *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x1400082f0  sub     rsp, 28h
0x1400082f4  mov     r9, rcx
0x1400082f7  test    r8, r8
0x1400082fa  jnz     short loc_140008306
0x1400082fc  mov     eax, 80004003h
0x140008301  jmp     loc_1400083B3
0x140008306  mov     rax, [rdx]
0x140008309  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x140008310  jnz     short loc_14000831D
0x140008312  mov     rax, [rdx+8]
0x140008316  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x14000831d  test    rax, rax
0x140008320  jz      short loc_14000839C
0x140008322  mov     rax, [rdx]
0x140008325  sub     rax, qword ptr cs:IID_IScriptletSite.Data1
0x14000832c  jnz     short loc_140008339
0x14000832e  mov     rax, [rdx+8]
0x140008332  sub     rax, qword ptr cs:IID_IScriptletSite.Data4
0x140008339  test    rax, rax
0x14000833c  jz      short loc_14000839C
0x14000833e  mov     rax, [rdx]
0x140008341  sub     rax, qword ptr cs:IID_IScriptletSitePoll.Data1
0x140008348  jnz     short loc_140008355
0x14000834a  mov     rax, [rdx+8]
0x14000834e  sub     rax, qword ptr cs:IID_IScriptletSitePoll.Data4
0x140008355  test    rax, rax
0x140008358  jnz     short loc_140008360
0x14000835a  add     rcx, 8
0x14000835e  jmp     short loc_140008380
0x140008360  mov     rax, [rdx]
0x140008363  sub     rax, qword ptr cs:IID_IScriptletSiteWSH.Data1
0x14000836a  jnz     short loc_140008377
0x14000836c  mov     rax, [rdx+8]
0x140008370  sub     rax, qword ptr cs:IID_IScriptletSiteWSH.Data4
0x140008377  test    rax, rax
0x14000837a  jnz     short loc_14000838E
0x14000837c  add     rcx, 10h
0x140008380  mov     rax, r9
0x140008383  neg     rax
0x140008386  sbb     rdx, rdx
0x140008389  and     rdx, rcx
0x14000838c  jmp     short loc_14000839F
0x14000838e  mov     qword ptr [r8], 0
0x140008395  mov     eax, 80004002h
0x14000839a  jmp     short loc_1400083B3
0x14000839c  mov     rdx, r9
0x14000839f  mov     [r8], rdx
0x1400083a2  mov     rcx, r9
0x1400083a5  mov     rax, [r9]
0x1400083a8  mov     rax, [rax+8]
0x1400083ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083b1  xor     eax, eax
0x1400083b3  add     rsp, 28h
0x1400083b7  retn
```
