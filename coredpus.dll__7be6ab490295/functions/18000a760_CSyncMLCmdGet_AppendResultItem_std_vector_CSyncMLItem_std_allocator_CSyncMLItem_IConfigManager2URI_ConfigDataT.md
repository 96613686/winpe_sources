# CSyncMLCmdGet::AppendResultItem(std::vector<CSyncMLItem *,std::allocator<CSyncMLItem *>> &,IConfigManager2URI *,ConfigDataType,ushort const *,ushort const *,int)

- ea: `0x18000a760`
- end: `0x18000ab86`
- name: `?AppendResultItem@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigManager2URI@@W4ConfigDataType@@PEBG3H@Z`
- size: `1062`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b560`
- `0x18000c600`
- `0x18000e1a0`

## callees

- `0x180003cf0`
- `0x180004220`
- `0x180004ab0`
- `0x18000a760`
- `0x1800128a0`
- `0x180014330`
- `0x1800145f0`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c87`
- `0x18001d670`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ab38`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ab38`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CSyncMLCmdGet::AppendResultItem(
        __int64 a1,
        const void **a2,
        __int64 a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7)
{
  _QWORD *v10; // rax
  __int64 v11; // rbx
  int v12; // esi
  _QWORD *v13; // rax
  __int64 *v14; // r12
  __int64 *v15; // rcx
  __int64 v16; // r15
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r13
  size_t v20; // r13
  _QWORD *v21; // r15
  void *v22; // rax
  __int64 *v23; // r8
  _BYTE *v24; // rdx
  void *v25; // rcx
  size_t v26; // r8
  _BYTE *v27; // rcx
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rax
  __int64 v31; // [rsp+30h] [rbp-88h]
  __int64 *v32; // [rsp+30h] [rbp-88h]
  __int64 v33; // [rsp+38h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  char *v36; // [rsp+60h] [rbp-58h]
  int v37; // [rsp+68h] [rbp-50h]
  int v38; // [rsp+6Ch] [rbp-4Ch]
  __int64 *v39; // [rsp+70h] [rbp-48h]
  __int64 v40; // [rsp+78h] [rbp-40h]

  v10 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = (__int64)v10;
  *(_QWORD *)&EventDescriptor.Id = v10;
  if ( v10 )
  {
    *v10 = &CSyncMLItem::`vftable';
    v10[1] = 0;
    v10[2] = 0;
    v10[3] = 0;
    v10[8] = 0;
    v10[9] = 0;
    v10[10] = 0;
    v10[11] = 0;
    *((_DWORD *)v10 + 24) = 0;
    *((_DWORD *)v10 + 25) = 15;
    v10[13] = 2;
    *((_DWORD *)v10 + 28) = 0;
    v10[4] = 0;
    v10[5] = 0;
    *((_OWORD *)v10 + 3) = 0;
    if ( !a3 )
    {
      v12 = -2147467261;
LABEL_36:
      (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
      goto LABEL_38;
    }
    v10[9] = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
    v12 = CSyncMLItem::SetFormat(v11, a4);
    if ( v12 < 0 )
      goto LABEL_36;
    v13 = *(_QWORD **)(v11 + 16);
    if ( !v13 )
    {
      v13 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v13 )
      {
        *(_QWORD *)(v11 + 16) = 0;
        v12 = -2147024882;
        goto LABEL_36;
      }
      v13[16] = 0;
      *(_OWORD *)v13 = 0;
      *((_OWORD *)v13 + 1) = 0;
      *((_OWORD *)v13 + 2) = 0;
      *((_OWORD *)v13 + 3) = 0;
      *((_OWORD *)v13 + 4) = 0;
      *((_OWORD *)v13 + 5) = 0;
      *((_OWORD *)v13 + 6) = 0;
      *((_OWORD *)v13 + 7) = 0;
      *(_QWORD *)(v11 + 16) = v13;
    }
    v12 = CSyncMLMeta::SetProperty((__int64)v13, 6, a5);
    if ( v12 < 0 )
      goto LABEL_36;
    v12 = CSyncMLItem::SetData((CSyncMLItem *)v11, a6);
    if ( v12 < 0 )
      goto LABEL_36;
    *(_DWORD *)(v11 + 108) = a7;
    v14 = (__int64 *)a2[1];
    v15 = (__int64 *)a2[2];
    if ( v14 != v15 )
    {
      *v14 = v11;
      a2[1] = (char *)a2[1] + 8;
      goto LABEL_38;
    }
    v16 = ((char *)v14 - (_BYTE *)*a2) >> 3;
    v31 = v16;
    if ( v16 == 0x1FFFFFFFFFFFFFFFLL )
      std::vector<CSyncMLCmd *>::_Xlength();
    v17 = ((char *)v15 - (_BYTE *)*a2) >> 3;
    v18 = v17 >> 1;
    if ( v17 <= 0x1FFFFFFFFFFFFFFFLL - (v17 >> 1) )
    {
      v33 = v16 + 1;
      v19 = v16 + 1;
      if ( v18 + v17 >= v16 + 1 )
        v19 = v18 + v17;
      if ( v19 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Throw_bad_array_new_length();
      v20 = 8 * v19;
      if ( !v20 )
      {
        v21 = 0;
        goto LABEL_25;
      }
      if ( v20 < 0x1000 )
      {
        v21 = operator new(v20);
        goto LABEL_25;
      }
      if ( v20 + 39 >= v20 )
      {
        v22 = operator new(v20 + 39);
        if ( !v22 )
          goto LABEL_32;
        v21 = (_QWORD *)(((unsigned __int64)v22 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v21 - 1) = v22;
LABEL_25:
        v32 = &v21[v31];
        *v32 = v11;
        v23 = (__int64 *)a2[1];
        v24 = *a2;
        v25 = v21;
        if ( v14 == v23 )
        {
          v26 = (char *)v23 - v24;
        }
        else
        {
          memmove_0(v21, v24, (char *)v14 - v24);
          v26 = (_BYTE *)a2[1] - (_BYTE *)v14;
          v25 = v32 + 1;
          v24 = v14;
        }
        memmove_0(v25, v24, v26);
        v27 = *a2;
        if ( !*a2 )
          goto LABEL_35;
        v28 = (const struct std::nothrow_t *)(8 * (((_BYTE *)a2[2] - v27) >> 3));
        if ( (unsigned __int64)v28 < 0x1000 )
        {
          v29 = (void *)*a2;
          goto LABEL_34;
        }
        v29 = (void *)*((_QWORD *)v27 - 1);
        if ( (unsigned __int64)(v27 - (_BYTE *)v29 - 8) <= 0x1F )
        {
          v28 = (const struct std::nothrow_t *)((char *)v28 + 39);
LABEL_34:
          operator delete(v29, v28);
LABEL_35:
          *a2 = v21;
          a2[1] = &v21[v33];
          a2[2] = &v21[v20 / 8];
          goto LABEL_38;
        }
LABEL_32:
        __fastfail(5u);
      }
    }
    std::_Throw_bad_array_new_length();
  }
  v12 = -2147024882;
LABEL_38:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v33) = v12;
    v39 = &v33;
    v40 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v36 = byte_180036BB9;
    v37 = 29;
    v38 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000a760  mov     [rsp+arg_0], rbx
0x18000a765  mov     [rsp+arg_10], rsi
0x18000a76a  push    rdi
0x18000a76b  push    r12
0x18000a76d  push    r13
0x18000a76f  push    r14
0x18000a771  push    r15
0x18000a773  sub     rsp, 90h
0x18000a77a  mov     rax, cs:__security_cookie
0x18000a781  xor     rax, rsp
0x18000a784  mov     [rsp+0B8h+var_38], rax
0x18000a78c  mov     r15d, r9d
0x18000a78f  mov     rsi, r8
0x18000a792  mov     r14, rdx
0x18000a795  mov     r13, [rsp+0B8h+arg_20]
0x18000a79d  mov     r12, [rsp+0B8h+arg_28]
0x18000a7a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7ac  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000a7b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7b6  mov     rbx, rax
0x18000a7b9  mov     qword ptr [rsp+0B8h+EventDescriptor.Id], rax
0x18000a7be  xor     edi, edi
0x18000a7c0  test    rax, rax
0x18000a7c3  jz      loc_18000AA82
0x18000a7c9  lea     rax, ??_7CSyncMLItem@@6B@; const CSyncMLItem::`vftable'
0x18000a7d0  mov     [rbx], rax
0x18000a7d3  mov     [rbx+8], rdi
0x18000a7d7  mov     [rbx+10h], rdi
0x18000a7db  mov     [rbx+18h], rdi
0x18000a7df  mov     [rbx+40h], rdi
0x18000a7e3  mov     [rbx+48h], rdi
0x18000a7e7  mov     [rbx+50h], rdi
0x18000a7eb  mov     [rbx+58h], rdi
0x18000a7ef  mov     [rbx+60h], edi
0x18000a7f2  mov     dword ptr [rbx+64h], 0Fh
0x18000a7f9  mov     qword ptr [rbx+68h], 2
0x18000a801  mov     [rbx+70h], edi
0x18000a804  xor     eax, eax
0x18000a806  mov     [rbx+20h], rax
0x18000a80a  mov     [rbx+28h], rax
0x18000a80e  xorps   xmm0, xmm0
0x18000a811  movups  xmmword ptr [rbx+30h], xmm0
0x18000a815  test    rsi, rsi
0x18000a818  jnz     short loc_18000A824
0x18000a81a  mov     esi, 80004003h
0x18000a81f  jmp     loc_18000AA6D
0x18000a824  mov     [rbx+48h], rsi
0x18000a828  mov     rax, [rsi]
0x18000a82b  mov     rcx, rsi
0x18000a82e  mov     rax, [rax+8]
0x18000a832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a837  mov     edx, r15d
0x18000a83a  mov     rcx, rbx
0x18000a83d  call    ?SetFormat@CSyncMLItem@@QEAAJW4ConfigDataType@@@Z; CSyncMLItem::SetFormat(ConfigDataType)
0x18000a842  mov     esi, eax
0x18000a844  test    eax, eax
0x18000a846  js      loc_18000AA6D
0x18000a84c  mov     rax, [rbx+10h]
0x18000a850  test    rax, rax
0x18000a853  jnz     short loc_18000A8A1
0x18000a855  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a85c  mov     ecx, 88h; unsigned __int64
0x18000a861  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a866  mov     [rsp+0B8h+var_88], rax
0x18000a86b  test    rax, rax
0x18000a86e  jz      loc_18000A8F5
0x18000a874  mov     [rax+80h], rdi
0x18000a87b  xorps   xmm0, xmm0
0x18000a87e  movups  xmmword ptr [rax], xmm0
0x18000a881  movups  xmmword ptr [rax+10h], xmm0
0x18000a885  movups  xmmword ptr [rax+20h], xmm0
0x18000a889  movups  xmmword ptr [rax+30h], xmm0
0x18000a88d  movups  xmmword ptr [rax+40h], xmm0
0x18000a891  movups  xmmword ptr [rax+50h], xmm0
0x18000a895  movups  xmmword ptr [rax+60h], xmm0
0x18000a899  movups  xmmword ptr [rax+70h], xmm0
0x18000a89d  mov     [rbx+10h], rax
0x18000a8a1  mov     r8, r13
0x18000a8a4  mov     edx, 6
0x18000a8a9  mov     rcx, rax
0x18000a8ac  call    ?SetProperty@CSyncMLMeta@@AEAAJW4SyncMLProp@@PEAX@Z; CSyncMLMeta::SetProperty(SyncMLProp,void *)
0x18000a8b1  mov     esi, eax
0x18000a8b3  test    eax, eax
0x18000a8b5  js      loc_18000AA6D
0x18000a8bb  mov     rdx, r12; unsigned __int16 *
0x18000a8be  mov     rcx, rbx; this
0x18000a8c1  call    ?SetData@CSyncMLItem@@QEAA?BJPEBG@Z; CSyncMLItem::SetData(ushort const *)
0x18000a8c6  mov     esi, eax
0x18000a8c8  test    eax, eax
0x18000a8ca  js      loc_18000AA6D
0x18000a8d0  mov     eax, [rsp+0B8h+arg_30]
0x18000a8d7  mov     [rbx+6Ch], eax
0x18000a8da  mov     r12, [r14+8]
0x18000a8de  mov     rcx, [r14+10h]
0x18000a8e2  cmp     r12, rcx
0x18000a8e5  jz      short loc_18000A903
0x18000a8e7  mov     [r12], rbx
0x18000a8eb  add     qword ptr [r14+8], 8
0x18000a8f0  jmp     loc_18000AA60
0x18000a8f5  mov     [rbx+10h], rdi
0x18000a8f9  mov     esi, 8007000Eh
0x18000a8fe  jmp     loc_18000AA6D
0x18000a903  mov     rax, [r14]
0x18000a906  mov     r15, r12
0x18000a909  sub     r15, rax
0x18000a90c  sar     r15, 3
0x18000a910  mov     [rsp+0B8h+var_88], r15
0x18000a915  mov     r9, 1FFFFFFFFFFFFFFFh
0x18000a91f  cmp     r15, r9
0x18000a922  jz      loc_18000AB74
0x18000a928  sub     rcx, rax
0x18000a92b  sar     rcx, 3
0x18000a92f  mov     rdx, rcx
0x18000a932  shr     rdx, 1
0x18000a935  mov     rax, r9
0x18000a938  sub     rax, rdx
0x18000a93b  cmp     rcx, rax
0x18000a93e  ja      loc_18000AB7F
0x18000a944  lea     r8, [r15+1]
0x18000a948  mov     [rsp+0B8h+var_80], r8
0x18000a94d  lea     rax, [rdx+rcx]
0x18000a951  mov     r13, r8
0x18000a954  cmp     rax, r8
0x18000a957  cmovnb  r13, rax
0x18000a95b  cmp     r13, r9
0x18000a95e  ja      loc_18000AB7A
0x18000a964  lea     r13, ds:0[r13*8]
0x18000a96c  test    r13, r13
0x18000a96f  jnz     short loc_18000A976
0x18000a971  mov     r15, rdi
0x18000a974  jmp     short loc_18000A9B3
0x18000a976  cmp     r13, 1000h
0x18000a97d  jb      short loc_18000A9A8
0x18000a97f  lea     rcx, [r13+27h]; Size
0x18000a983  cmp     rcx, r13
0x18000a986  jbe     loc_18000AB7F
0x18000a98c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a991  test    rax, rax
0x18000a994  jz      loc_18000AA36
0x18000a99a  lea     r15, [rax+27h]
0x18000a99e  and     r15, 0FFFFFFFFFFFFFFE0h
0x18000a9a2  mov     [r15-8], rax
0x18000a9a6  jmp     short loc_18000A9B3
0x18000a9a8  mov     rcx, r13; Size
0x18000a9ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9b0  mov     r15, rax
0x18000a9b3  mov     rax, [rsp+0B8h+var_88]
0x18000a9b8  lea     rax, [r15+rax*8]
0x18000a9bc  mov     [rsp+0B8h+var_88], rax
0x18000a9c1  mov     [rax], rbx
0x18000a9c4  mov     r8, [r14+8]
0x18000a9c8  mov     rdx, [r14]; Src
0x18000a9cb  mov     rcx, r15; void *
0x18000a9ce  cmp     r12, r8
0x18000a9d1  jnz     short loc_18000A9D8
0x18000a9d3  sub     r8, rdx
0x18000a9d6  jmp     short loc_18000A9F6
0x18000a9d8  mov     r8, r12
0x18000a9db  sub     r8, rdx; Size
0x18000a9de  call    memmove_0
0x18000a9e3  mov     r8, [r14+8]
0x18000a9e7  sub     r8, r12; Size
0x18000a9ea  mov     rcx, [rsp+0B8h+var_88]
0x18000a9ef  add     rcx, 8; void *
0x18000a9f3  mov     rdx, r12; Src
0x18000a9f6  call    memmove_0
0x18000a9fb  mov     rcx, [r14]
0x18000a9fe  test    rcx, rcx
0x18000aa01  jz      short loc_18000AA48
0x18000aa03  mov     rax, [r14+10h]
0x18000aa07  sub     rax, rcx
0x18000aa0a  sar     rax, 3
0x18000aa0e  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000aa16  cmp     rdx, 1000h
0x18000aa1d  jb      short loc_18000AA3D
0x18000aa1f  mov     rax, [rcx-8]
0x18000aa23  sub     rcx, rax
0x18000aa26  sub     rcx, 8
0x18000aa2a  cmp     rcx, 1Fh
0x18000aa2e  ja      short loc_18000AA36
0x18000aa30  add     rdx, 27h ; '''
0x18000aa34  jmp     short loc_18000AA40
0x18000aa36  mov     ecx, 5
0x18000aa3b  int     29h; Win8: RtlFailFast(ecx)
0x18000aa3d  mov     rax, rcx
0x18000aa40  mov     rcx, rax; void *
0x18000aa43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000aa48  mov     [r14], r15
0x18000aa4b  mov     rax, [rsp+0B8h+var_80]
0x18000aa50  lea     rax, [r15+rax*8]
0x18000aa54  mov     [r14+8], rax
0x18000aa58  lea     rax, [r15+r13]
0x18000aa5c  mov     [r14+10h], rax
0x18000aa60  jmp     short loc_18000AA87
0x18000aa62  mov     rbx, qword ptr [rsp+0B8h+EventDescriptor.Id]
0x18000aa67  xor     edi, edi
0x18000aa69  mov     esi, dword ptr [rsp+0B8h+var_80]
0x18000aa6d  mov     rax, [rbx]
0x18000aa70  mov     edx, 1
0x18000aa75  mov     rcx, rbx
0x18000aa78  mov     rax, [rax]
0x18000aa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa80  jmp     short loc_18000AA87
0x18000aa82  mov     esi, 8007000Eh
0x18000aa87  mov     eax, cs:dword_18003E048
0x18000aa8d  cmp     eax, 5
0x18000aa90  jbe     loc_18000AB44
0x18000aa96  mov     dword ptr [rsp+0B8h+var_80], esi
0x18000aa9a  lea     rax, [rsp+0B8h+var_80]
0x18000aa9f  mov     [rsp+0B8h+var_48], rax
0x18000aaa4  mov     [rsp+0B8h+var_40], 4
0x18000aaad  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x18000aab5  movzx   eax, cs:word_180036BAF
0x18000aabc  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x18000aac0  mov     [rsp+0B8h+EventDescriptor.Keyword], rdi
0x18000aac5  mov     rax, cs:off_18003E050
0x18000aacc  mov     [rsp+0B8h+var_68.Ptr], rax
0x18000aad1  movzx   eax, word ptr [rax]
0x18000aad4  mov     [rsp+0B8h+var_68.Size], eax
0x18000aad8  mov     dword ptr [rsp+0B8h+var_68.0Ch], 2
0x18000aae0  lea     rax, byte_180036BB9
0x18000aae7  mov     [rsp+0B8h+var_58], rax
0x18000aaec  mov     [rsp+0B8h+var_50], 1Dh
0x18000aaf4  mov     [rsp+0B8h+var_4C], 1
0x18000aafc  lea     rax, _TraceLoggingMetadataEnd
0x18000ab03  lea     rcx, _TraceLoggingMetadata
0x18000ab0a  sub     eax, ecx
0x18000ab0c  mov     dword ptr [rsp+0B8h+var_88], eax
0x18000ab10  mov     eax, dword ptr [rsp+0B8h+var_88]
0x18000ab14  lea     rax, [rsp+0B8h+var_68]
0x18000ab19  mov     [rsp+0B8h+UserData], rax; UserData
0x18000ab1e  mov     [rsp+0B8h+UserDataCount], 3; UserDataCount
0x18000ab26  xor     r9d, r9d; RelatedActivityId
0x18000ab29  xor     r8d, r8d; ActivityId
0x18000ab2c  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x18000ab31  mov     rcx, cs:RegHandle; RegHandle
0x18000ab38  call    cs:__imp_EventWriteTransfer
0x18000ab3f  nop     dword ptr [rax+rax+00h]
0x18000ab44  mov     eax, esi
0x18000ab46  mov     rcx, [rsp+0B8h+var_38]
0x18000ab4e  xor     rcx, rsp; StackCookie
0x18000ab51  call    __security_check_cookie
0x18000ab56  lea     r11, [rsp+0B8h+var_28]
0x18000ab5e  mov     rbx, [r11+30h]
0x18000ab62  mov     rsi, [r11+40h]
0x18000ab66  mov     rsp, r11
0x18000ab69  pop     r15
0x18000ab6b  pop     r14
0x18000ab6d  pop     r13
0x18000ab6f  pop     r12
0x18000ab71  pop     rdi
0x18000ab72  retn
0x18000ab74  call    ?_Xlength@?$vector@PEAVCSyncMLCmd@@V?$allocator@PEAVCSyncMLCmd@@@std@@@std@@CAXXZ; std::vector<CSyncMLCmd *>::_Xlength(void)
0x18000ab7a  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000ab7f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
