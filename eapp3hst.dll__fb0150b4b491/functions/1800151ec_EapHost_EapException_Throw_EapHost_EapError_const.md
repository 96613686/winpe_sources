# EapHost::EapException::Throw(EapHost::EapError const &)

- ea: `0x1800151ec`
- end: `0x180015496`
- name: `?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z`
- size: `682`
- prototype: `void __fastcall __noreturn(const struct EapHost::EapError *)`
- caller_count: `30`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001549c`
- `0x1800154dc`
- `0x180015534`
- `0x1800155dc`
- `0x18001617c`
- `0x18001e8b0`
- `0x18001eb30`
- `0x18001ecb0`
- `0x18001ede0`
- `0x18001efa0`
- `0x18001f170`
- `0x18001f360`
- `0x18001f440`
- `0x18001f5a0`
- `0x18001f680`
- `0x18001f7e0`
- `0x18001f990`
- `0x18001fb30`
- `0x1800280d0`
- `0x1800287c0`
- `0x180028a60`
- `0x180028b60`
- `0x180028c90`
- `0x180028ec0`
- `0x180029040`
- `0x180029170`
- `0x1800292a0`
- `0x18002c590`
- `0x18002c728`
- `0x18002e494`

## callees

- `0x18000213c`
- `0x180003b38`
- `0x180003e38`
- `0x18000439c`
- `0x1800126f8`
- `0x1800138f8`
- `0x180013d10`
- `0x1800150f4`
- `0x1800151ec`
- `0x180015650`
- `0x180015818`
- `0x1800158c4`
- `0x18002f4a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015387`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015399`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800153ab`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015387`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015399`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800153ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn EapHost::EapException::Throw(const struct EapHost::EapError *a1)
{
  char v2; // di
  int v3; // esi
  __int64 v4; // rdx
  char *v5; // r8
  int v6; // edx
  int v7; // r8d
  void *v8; // rdi
  __int64 *v9; // rbx
  _QWORD *v10; // rcx
  __int64 *v11; // r9
  __int64 *v12; // rax
  void *v13; // [rsp+30h] [rbp-D0h] BYREF
  void *v14; // [rsp+38h] [rbp-C8h] BYREF
  GUID *v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID *v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  GUID *rguid[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[8]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+88h] [rbp-78h]
  _BYTE v21[96]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR pExceptionObject[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v23; // [rsp+F8h] [rbp-8h]
  _BYTE v24[96]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR v25[40]; // [rsp+160h] [rbp+60h] BYREF
  OLECHAR sz[48]; // [rsp+1B0h] [rbp+B0h] BYREF

  v2 = 0;
  LODWORD(v13) = 0;
  EapHost::EapException::EapException((EapHost::EapException *)v19, a1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    rguid[0] = 0;
    rguid[1] = 0;
    v16[0] = 0;
    v16[1] = 0;
    v15[0] = 0;
    v15[1] = 0;
    v13 = 0;
    v14 = 0;
    TempBuffer<0>::Assign((__int64)rguid, 0x10u, (char *)a1 + 24);
    TempBuffer<0>::Assign((__int64)v16, 0x10u, (char *)a1 + 40);
    TempBuffer<0>::Assign((__int64)v15, 0x10u, (char *)a1 + 56);
    BasicSimpleString<wchar_t>::Assign(&v13, *((_QWORD *)a1 + 9));
    BasicSimpleString<wchar_t>::Assign(&v14, *((_QWORD *)a1 + 10));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = *((_DWORD *)a1 + 5);
      v5 = (char *)HeapAllocator::Alloc(0x20u);
      if ( v5 )
      {
        *(_QWORD *)v5 = &EapHost::EapType::`vftable';
        LOBYTE(v4) = *((_BYTE *)a1 + 4);
        v5[8] = v4;
        *((_DWORD *)v5 + 3) = *((_DWORD *)a1 + 2);
        *((_DWORD *)v5 + 4) = *((_DWORD *)a1 + 3);
        if ( (_BYTE)v4 != 0xFE )
          *(_QWORD *)(v5 + 12) = 0;
        *(_QWORD *)v5 = &EapHost::EapMethodType::`vftable';
        *((_DWORD *)v5 + 6) = *((_DWORD *)a1 + 4);
      }
      else
      {
        v5 = 0;
      }
      v18 = (__int64 (__fastcall ***)(_QWORD, __int64))v5;
      v2 = 3;
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *(unsigned int *)a1, (unsigned __int8)v5[8], v3);
    }
    if ( (v2 & 1) != 0 )
      std::unique_ptr<EapLm::Peer::ThirdPartyDispatcherSession>::~unique_ptr<EapLm::Peer::ThirdPartyDispatcherSession>(&v18);
    memset_0(sz, 0, 0x4Eu);
    memset_0(v25, 0, 0x4Eu);
    StringFromGUID2(rguid[0], sz, 39);
    StringFromGUID2(v16[0], v25, 39);
    StringFromGUID2(v15[0], pExceptionObject, 39);
    v8 = v13;
    v9 = (__int64 *)v14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          v7,
          (unsigned int)sz,
          (__int64)v25,
          (__int64)pExceptionObject);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      {
        v11 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
        v12 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
        if ( v9 )
          v12 = v9;
        if ( v8 )
          LODWORD(v11) = (_DWORD)v8;
        WPP_SF_SS(v10[2], 13, (int)WPP_03e33dbf1b4032e614116b7bba0efbaf_Traceguids, (int)v11, (__int64)v12);
      }
    }
    HeapAllocator::Free(v9);
    HeapAllocator::Free(v8);
    HeapAllocator::Free(v15[0]);
    HeapAllocator::Free(v16[0]);
    HeapAllocator::Free(rguid[0]);
  }
  v23 = v20;
  *(_QWORD *)pExceptionObject = &EapHost::EapException::`vftable';
  EapHost::EapError::EapError((EapHost::EapError *)v24, (const struct EapHost::EapError *)v21);
  throw (EapHost::EapException *)pExceptionObject;
}

```

## disassembly

```asm
0x1800151ec  mov     [rsp-8+arg_8], rbx
0x1800151f1  mov     [rsp-8+arg_10], rsi
0x1800151f6  push    rbp
0x1800151f7  push    rdi
0x1800151f8  push    r12
0x1800151fa  lea     rbp, [rsp-100h]
0x180015202  sub     rsp, 200h
0x180015209  mov     rbx, rcx
0x18001520c  xor     edi, edi
0x18001520e  mov     dword ptr [rsp+210h+var_1E0], edi
0x180015212  mov     rdx, rcx; struct EapHost::EapError *
0x180015215  lea     rcx, [rbp+110h+var_190]; this
0x180015219  call    ??0EapException@EapHost@@QEAA@AEBVEapError@1@@Z; EapHost::EapException::EapException(EapHost::EapError const &)
0x18001521e  nop
0x18001521f  mov     rax, cs:WPP_GLOBAL_Control
0x180015226  test    byte ptr [rax+1Ch], 1
0x18001522a  jz      loc_180015466
0x180015230  mov     [rsp+210h+rguid], rdi
0x180015235  mov     [rsp+210h+var_1A8], rdi
0x18001523a  mov     [rsp+210h+var_1C0], rdi
0x18001523f  mov     [rsp+210h+var_1B8], rdi
0x180015244  mov     [rsp+210h+var_1D0], rdi
0x180015249  mov     [rsp+210h+var_1C8], rdi
0x18001524e  mov     [rsp+210h+var_1E0], rdi
0x180015253  mov     [rsp+210h+var_1D8], rdi
0x180015258  lea     r8, [rbx+18h]
0x18001525c  lea     esi, [rdi+10h]
0x18001525f  mov     edx, esi
0x180015261  lea     rcx, [rsp+210h+rguid]
0x180015266  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001526b  lea     r8, [rbx+28h]
0x18001526f  mov     edx, esi
0x180015271  lea     rcx, [rsp+210h+var_1C0]
0x180015276  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001527b  lea     r8, [rbx+38h]
0x18001527f  mov     edx, esi
0x180015281  lea     rcx, [rsp+210h+var_1D0]
0x180015286  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001528b  mov     rdx, [rbx+48h]
0x18001528f  lea     rcx, [rsp+210h+var_1E0]
0x180015294  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180015299  mov     rdx, [rbx+50h]
0x18001529d  lea     rcx, [rsp+210h+var_1D8]
0x1800152a2  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800152a7  lea     r12, WPP_GLOBAL_Control
0x1800152ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800152b5  cmp     rax, r12
0x1800152b8  jz      loc_18001533F
0x1800152be  test    byte ptr [rax+1Ch], 1
0x1800152c2  jz      short loc_18001533F
0x1800152c4  mov     esi, [rbx+14h]
0x1800152c7  lea     ecx, [rdi+20h]; unsigned __int64
0x1800152ca  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800152cf  mov     r8, rax
0x1800152d2  test    rax, rax
0x1800152d5  jz      short loc_180015312
0x1800152d7  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x1800152de  mov     [r8], rax
0x1800152e1  mov     dl, [rbx+4]
0x1800152e4  mov     [r8+8], dl
0x1800152e8  mov     ecx, [rbx+8]
0x1800152eb  mov     [r8+0Ch], ecx
0x1800152ef  mov     ecx, [rbx+0Ch]
0x1800152f2  mov     [r8+10h], ecx
0x1800152f6  cmp     dl, 0FEh
0x1800152f9  jz      short loc_1800152FF
0x1800152fb  mov     [r8+0Ch], rdi
0x1800152ff  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180015306  mov     [r8], rax
0x180015309  mov     eax, [rbx+10h]
0x18001530c  mov     [r8+18h], eax
0x180015310  jmp     short loc_180015315
0x180015312  xor     r8d, r8d
0x180015315  mov     [rsp+210h+var_1A0], r8
0x18001531a  mov     edi, 3
0x18001531f  movzx   eax, byte ptr [r8+8]
0x180015324  mov     dword ptr [rsp+210h+var_1E8], esi
0x180015328  mov     dword ptr [rsp+210h+var_1F0], eax
0x18001532c  mov     r9d, [rbx]
0x18001532f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015336  mov     rcx, [rcx+10h]
0x18001533a  call    WPP_SF_DDD
0x18001533f  test    dil, 1
0x180015343  jz      short loc_18001534F
0x180015345  lea     rcx, [rsp+210h+var_1A0]
0x18001534a  call    ??1?$unique_ptr@VThirdPartyDispatcherSession@Peer@EapLm@@U?$default_delete@VThirdPartyDispatcherSession@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::ThirdPartyDispatcherSession>::~unique_ptr<EapLm::Peer::ThirdPartyDispatcherSession>(void)
0x18001534f  mov     ebx, 4Eh ; 'N'
0x180015354  mov     r8d, ebx; Size
0x180015357  xor     edx, edx; Val
0x180015359  lea     rcx, [rbp+110h+sz]; void *
0x180015360  call    memset_0
0x180015365  mov     r8d, ebx; Size
0x180015368  xor     edx, edx; Val
0x18001536a  lea     rcx, [rbp+110h+var_B0]; void *
0x18001536e  call    memset_0
0x180015373  mov     ebx, 27h ; '''
0x180015378  mov     r8d, ebx; cchMax
0x18001537b  lea     rdx, [rbp+110h+sz]; lpsz
0x180015382  mov     rcx, [rsp+210h+rguid]; rguid
0x180015387  call    cs:__imp_StringFromGUID2
0x18001538d  mov     r8d, ebx; cchMax
0x180015390  lea     rdx, [rbp+110h+var_B0]; lpsz
0x180015394  mov     rcx, [rsp+210h+var_1C0]; rguid
0x180015399  call    cs:__imp_StringFromGUID2
0x18001539f  mov     r8d, ebx; cchMax
0x1800153a2  lea     rdx, [rbp+110h+pExceptionObject]; lpsz
0x1800153a6  mov     rcx, [rsp+210h+var_1D0]; rguid
0x1800153ab  call    cs:__imp_StringFromGUID2
0x1800153b1  mov     rdi, [rsp+210h+var_1E0]
0x1800153b6  mov     rbx, [rsp+210h+var_1D8]
0x1800153bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153c2  cmp     rcx, r12
0x1800153c5  jz      short loc_180015434
0x1800153c7  test    byte ptr [rcx+1Ch], 1
0x1800153cb  jz      short loc_1800153F6
0x1800153cd  lea     rax, [rbp+110h+pExceptionObject]
0x1800153d1  mov     [rsp+210h+var_1E8], rax
0x1800153d6  lea     rax, [rbp+110h+var_B0]
0x1800153da  mov     [rsp+210h+var_1F0], rax
0x1800153df  lea     r9, [rbp+110h+sz]
0x1800153e6  mov     rcx, [rcx+10h]
0x1800153ea  call    WPP_SF_SSS
0x1800153ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153f6  cmp     rcx, r12
0x1800153f9  jz      short loc_180015434
0x1800153fb  test    byte ptr [rcx+1Ch], 1
0x1800153ff  jz      short loc_180015434
0x180015401  lea     r9, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180015408  mov     rax, r9
0x18001540b  test    rbx, rbx
0x18001540e  cmovnz  rax, rbx
0x180015412  test    rdi, rdi
0x180015415  cmovnz  r9, rdi
0x180015419  mov     edx, 0Dh
0x18001541e  mov     [rsp+210h+var_1F0], rax
0x180015423  lea     r8, WPP_03e33dbf1b4032e614116b7bba0efbaf_Traceguids
0x18001542a  mov     rcx, [rcx+10h]
0x18001542e  call    WPP_SF_SS
0x180015433  nop
0x180015434  mov     rcx, rbx; void *
0x180015437  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001543c  nop
0x18001543d  mov     rcx, rdi; void *
0x180015440  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180015445  nop
0x180015446  mov     rcx, [rsp+210h+var_1D0]; void *
0x18001544b  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180015450  nop
0x180015451  mov     rcx, [rsp+210h+var_1C0]; void *
0x180015456  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001545b  nop
0x18001545c  mov     rcx, [rsp+210h+rguid]; void *
0x180015461  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180015466  mov     eax, [rbp+110h+var_188]
0x180015469  mov     [rbp+110h+var_118], eax
0x18001546c  lea     rax, ??_7EapException@EapHost@@6B@; const EapHost::EapException::`vftable'
0x180015473  mov     qword ptr [rbp+110h+pExceptionObject], rax
0x180015477  lea     rdx, [rbp+110h+var_180]; struct EapHost::EapError *
0x18001547b  lea     rcx, [rbp+110h+var_110]; this
0x18001547f  call    ??0EapError@EapHost@@QEAA@AEBV01@@Z; EapHost::EapError::EapError(EapHost::EapError const &)
0x180015484  nop
0x180015485  lea     rdx, _TI3?AVEapException@EapHost@@; pThrowInfo
0x18001548c  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x180015490  call    _CxxThrowException_0
```
