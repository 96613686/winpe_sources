# CPropPage::CPropPage(ushort const *,ushort *)

- ea: `0x180017f60`
- end: `0x180018013`
- name: `??0CPropPage@@QEAA@PEBGPEAG@Z`
- size: `179`
- prototype: `CPropPage *__fastcall(CPropPage *__hidden this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010264`
- `0x180012c38`
- `0x180016e14`

## callees

- `0x180001840`
- `0x180017f60`

## pseudocode

```c
CPropPage *__fastcall CPropPage::CPropPage(CPropPage *this, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v4; // r11
  _BYTE *v5; // rax
  __int64 v6; // rcx

  *((_QWORD *)this + 14) = 0;
  *(_QWORD *)this = &CPropPage::`vftable';
  *((_QWORD *)this + 15) = 0;
  _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
  *(_QWORD *)((char *)this + 132) = 0;
  *((_BYTE *)this + 662) = 0;
  StringCchCopyW((unsigned __int16 *)this + 70, 0x105u, a3);
  v5 = (_BYTE *)(v3 + 8);
  v6 = 104;
  do
  {
    *v5++ = 0;
    --v6;
  }
  while ( v6 );
  *(_QWORD *)(v3 + 16) = g_hInstance;
  *(_QWORD *)(v3 + 48) = CPropPage::StaticDlgProc;
  *(_QWORD *)(v3 + 64) = CPropPage::PageRelease;
  *(_DWORD *)(v3 + 8) = 104;
  *(_DWORD *)(v3 + 12) = 16512;
  *(_QWORD *)(v3 + 24) = v4;
  *(_QWORD *)(v3 + 72) = 0;
  *(_QWORD *)(v3 + 56) = v3;
  *(_QWORD *)(v3 + 96) = g_hActCtx;
  return (CPropPage *)v3;
}

```

## disassembly

```asm
0x180017f60  sub     rsp, 28h
0x180017f64  lea     rax, ??_7CPropPage@@6B@; const CPropPage::`vftable'
0x180017f6b  mov     qword ptr [rcx+70h], 0
0x180017f73  mov     [rcx], rax
0x180017f76  mov     r11, rdx
0x180017f79  mov     r10, rcx
0x180017f7c  mov     qword ptr [rcx+78h], 0
0x180017f84  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180017f8b  mov     qword ptr [rcx+84h], 0
0x180017f96  mov     edx, 105h; unsigned __int64
0x180017f9b  mov     byte ptr [rcx+296h], 0
0x180017fa2  add     rcx, 8Ch; unsigned __int16 *
0x180017fa9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017fae  mov     r8d, 68h ; 'h'
0x180017fb4  lea     rax, [r10+8]
0x180017fb8  mov     ecx, r8d
0x180017fbb  mov     byte ptr [rax], 0
0x180017fbe  inc     rax
0x180017fc1  sub     rcx, 1
0x180017fc5  jnz     short loc_180017FBB
0x180017fc7  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180017fce  mov     [r10+10h], rax
0x180017fd2  lea     rax, ?StaticDlgProc@CPropPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropPage::StaticDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180017fd9  mov     [r10+30h], rax
0x180017fdd  lea     rax, ?PageRelease@CPropPage@@CAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; CPropPage::PageRelease(HWND__ *,uint,_PROPSHEETPAGEW *)
0x180017fe4  mov     [r10+40h], rax
0x180017fe8  mov     [r10+8], r8d
0x180017fec  mov     dword ptr [r10+0Ch], 4080h
0x180017ff4  mov     [r10+18h], r11
0x180017ff8  mov     [r10+48h], rcx
0x180017ffc  mov     [r10+38h], r10
0x180018000  mov     rax, cs:?g_hActCtx@@3PEAXEA; void * g_hActCtx
0x180018007  mov     [r10+60h], rax
0x18001800b  mov     rax, r10
0x18001800e  add     rsp, 28h
0x180018012  retn
```
