# EapHost::EapException::Throw(EapHost::EapError const &)

- ea: `0x18001e4ac`
- end: `0x18001e720`
- name: `?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z`
- size: `628`
- prototype: `void __fastcall __noreturn(const struct EapHost::EapError *)`
- caller_count: `17`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180018250`
- `0x180018990`
- `0x180018c40`
- `0x180018d40`
- `0x180018e80`
- `0x1800190d0`
- `0x180019260`
- `0x180019390`
- `0x1800194c0`
- `0x18001b67c`
- `0x18001b9a8`
- `0x18001da14`
- `0x18001e728`
- `0x18001e768`
- `0x18001e7c0`
- `0x18001e868`
- `0x180037fa4`

## callees

- `0x1800034cc`
- `0x180004fb8`
- `0x180005410`
- `0x180007564`
- `0x18001d490`
- `0x18001e288`
- `0x18001e3e0`
- `0x18001e4ac`
- `0x18001e8e8`
- `0x18001ea30`
- `0x18001f614`
- `0x180030f54`
- `0x180035114`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e5ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e617`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e62f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e5ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e617`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001e62f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn EapHost::EapException::Throw(const struct EapHost::EapError *a1)
{
  char v2; // si
  int v3; // ebx
  __int64 EapType; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // edx
  int v8; // r8d
  void *v9; // rdi
  __int64 *v10; // rbx
  EapHost::Peer::Host *v11; // rcx
  __int64 *v12; // r9
  __int64 *v13; // rax
  void *v14; // [rsp+30h] [rbp-D0h] BYREF
  void *v15; // [rsp+38h] [rbp-C8h] BYREF
  GUID *v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID *v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  GUID *rguid[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v19[2])(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[8]; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+88h] [rbp-78h]
  _BYTE v22[96]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR pExceptionObject[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v24; // [rsp+F8h] [rbp-8h]
  _BYTE v25[96]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR v26[40]; // [rsp+160h] [rbp+60h] BYREF
  OLECHAR sz[48]; // [rsp+1B0h] [rbp+B0h] BYREF

  v2 = 0;
  LODWORD(v14) = 0;
  EapHost::EapException::EapException((EapHost::EapException *)v20, a1);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    rguid[0] = 0;
    rguid[1] = 0;
    v17[0] = 0;
    v17[1] = 0;
    v16[0] = 0;
    v16[1] = 0;
    v14 = 0;
    v15 = 0;
    TempBuffer<0>::Assign((__int64)rguid, 0x10u, (char *)a1 + 24);
    TempBuffer<0>::Assign((__int64)v17, 0x10u, (char *)a1 + 40);
    TempBuffer<0>::Assign((__int64)v16, 0x10u, (char *)a1 + 56);
    BasicSimpleString<wchar_t>::Assign(&v14, *((_QWORD *)a1 + 9));
    BasicSimpleString<wchar_t>::Assign(&v15, *((_QWORD *)a1 + 10));
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = *((_DWORD *)a1 + 5);
      EapType = EapHost::EapError::GetEapType(a1, v19);
      v2 = 1;
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v6,
        *(unsigned int *)a1,
        *(unsigned __int8 *)(*(_QWORD *)EapType + 8LL),
        v3);
    }
    if ( (v2 & 1) != 0 )
      std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(v19);
    memset_0(sz, 0, 0x4Eu);
    memset_0(v26, 0, 0x4Eu);
    StringFromGUID2(rguid[0], sz, 39);
    StringFromGUID2(v17[0], v26, 39);
    StringFromGUID2(v16[0], pExceptionObject, 39);
    v9 = v14;
    v10 = (__int64 *)v15;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SSS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          v8,
          (unsigned int)sz,
          (__int64)v26,
          (__int64)pExceptionObject);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v12 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
        v13 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
        if ( v10 )
          v13 = v10;
        if ( v9 )
          LODWORD(v12) = (_DWORD)v9;
        WPP_SF_SS(
          *((_QWORD *)v11 + 2),
          13,
          (unsigned int)WPP_03e33dbf1b4032e614116b7bba0efbaf_Traceguids,
          (_DWORD)v12,
          (__int64)v13);
      }
    }
    HeapAllocator::Free(v10);
    HeapAllocator::Free(v9);
    HeapAllocator::Free(v16[0]);
    HeapAllocator::Free(v17[0]);
    HeapAllocator::Free(rguid[0]);
  }
  v24 = v21;
  *(_QWORD *)pExceptionObject = &EapHost::EapException::`vftable';
  EapHost::EapError::EapError((EapHost::EapError *)v25, (const struct EapHost::EapError *)v22);
  throw (EapHost::EapException *)pExceptionObject;
}

```

## disassembly

```asm
0x18001e4ac  mov     [rsp-8+arg_8], rbx
0x18001e4b1  mov     [rsp-8+arg_10], rsi
0x18001e4b6  push    rbp
0x18001e4b7  push    rdi
0x18001e4b8  push    r12
0x18001e4ba  lea     rbp, [rsp-100h]
0x18001e4c2  sub     rsp, 200h
0x18001e4c9  mov     rdi, rcx
0x18001e4cc  xor     esi, esi
0x18001e4ce  mov     dword ptr [rsp+210h+var_1E0], esi
0x18001e4d2  mov     rdx, rcx; struct EapHost::EapError *
0x18001e4d5  lea     rcx, [rbp+110h+var_190]; this
0x18001e4d9  call    ??0EapException@EapHost@@QEAA@AEBVEapError@1@@Z; EapHost::EapException::EapException(EapHost::EapError const &)
0x18001e4de  nop
0x18001e4df  mov     rax, cs:WPP_GLOBAL_Control
0x18001e4e6  test    byte ptr [rax+1Ch], 1
0x18001e4ea  jz      loc_18001E6F0
0x18001e4f0  mov     [rsp+210h+rguid], rsi
0x18001e4f5  mov     [rsp+210h+var_1A8], rsi
0x18001e4fa  mov     [rsp+210h+var_1C0], rsi
0x18001e4ff  mov     [rsp+210h+var_1B8], rsi
0x18001e504  mov     [rsp+210h+var_1D0], rsi
0x18001e509  mov     [rsp+210h+var_1C8], rsi
0x18001e50e  mov     [rsp+210h+var_1E0], rsi
0x18001e513  mov     [rsp+210h+var_1D8], rsi
0x18001e518  lea     r8, [rdi+18h]
0x18001e51c  lea     ebx, [rsi+10h]
0x18001e51f  mov     edx, ebx
0x18001e521  lea     rcx, [rsp+210h+rguid]
0x18001e526  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001e52b  lea     r8, [rdi+28h]
0x18001e52f  mov     edx, ebx
0x18001e531  lea     rcx, [rsp+210h+var_1C0]
0x18001e536  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001e53b  lea     r8, [rdi+38h]
0x18001e53f  mov     edx, ebx
0x18001e541  lea     rcx, [rsp+210h+var_1D0]
0x18001e546  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001e54b  mov     rdx, [rdi+48h]
0x18001e54f  lea     rcx, [rsp+210h+var_1E0]
0x18001e554  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001e559  mov     rdx, [rdi+50h]
0x18001e55d  lea     rcx, [rsp+210h+var_1D8]
0x18001e562  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001e567  lea     r12, WPP_GLOBAL_Control
0x18001e56e  mov     rax, cs:WPP_GLOBAL_Control
0x18001e575  cmp     rax, r12
0x18001e578  jz      short loc_18001E5B7
0x18001e57a  test    byte ptr [rax+1Ch], 1
0x18001e57e  jz      short loc_18001E5B7
0x18001e580  mov     ebx, [rdi+14h]
0x18001e583  lea     rdx, [rsp+210h+var_1A0]
0x18001e588  mov     rcx, rdi
0x18001e58b  call    ?GetEapType@EapError@EapHost@@QEBA?AV?$unique_ptr@VEapMethodType@EapHost@@U?$default_delete@VEapMethodType@EapHost@@@std@@@std@@XZ; EapHost::EapError::GetEapType(void)
0x18001e590  mov     esi, 1
0x18001e595  mov     rax, [rax]
0x18001e598  movzx   ecx, byte ptr [rax+8]
0x18001e59c  mov     dword ptr [rsp+210h+var_1E8], ebx
0x18001e5a0  mov     dword ptr [rsp+210h+var_1F0], ecx
0x18001e5a4  mov     r9d, [rdi]
0x18001e5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5ae  mov     rcx, [rcx+10h]
0x18001e5b2  call    WPP_SF_DDD
0x18001e5b7  test    sil, 1
0x18001e5bb  jz      short loc_18001E5C7
0x18001e5bd  lea     rcx, [rsp+210h+var_1A0]
0x18001e5c2  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x18001e5c7  mov     ebx, 4Eh ; 'N'
0x18001e5cc  mov     r8d, ebx; Size
0x18001e5cf  xor     edx, edx; Val
0x18001e5d1  lea     rcx, [rbp+110h+sz]; void *
0x18001e5d8  call    memset_0
0x18001e5dd  mov     r8d, ebx; Size
0x18001e5e0  xor     edx, edx; Val
0x18001e5e2  lea     rcx, [rbp+110h+var_B0]; void *
0x18001e5e6  call    memset_0
0x18001e5eb  mov     ebx, 27h ; '''
0x18001e5f0  mov     r8d, ebx; cchMax
0x18001e5f3  lea     rdx, [rbp+110h+sz]; lpsz
0x18001e5fa  mov     rcx, [rsp+210h+rguid]; rguid
0x18001e5ff  call    cs:__imp_StringFromGUID2
0x18001e606  nop     dword ptr [rax+rax+00h]
0x18001e60b  mov     r8d, ebx; cchMax
0x18001e60e  lea     rdx, [rbp+110h+var_B0]; lpsz
0x18001e612  mov     rcx, [rsp+210h+var_1C0]; rguid
0x18001e617  call    cs:__imp_StringFromGUID2
0x18001e61e  nop     dword ptr [rax+rax+00h]
0x18001e623  mov     r8d, ebx; cchMax
0x18001e626  lea     rdx, [rbp+110h+pExceptionObject]; lpsz
0x18001e62a  mov     rcx, [rsp+210h+var_1D0]; rguid
0x18001e62f  call    cs:__imp_StringFromGUID2
0x18001e636  nop     dword ptr [rax+rax+00h]
0x18001e63b  mov     rdi, [rsp+210h+var_1E0]
0x18001e640  mov     rbx, [rsp+210h+var_1D8]
0x18001e645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e64c  cmp     rcx, r12
0x18001e64f  jz      short loc_18001E6BE
0x18001e651  test    byte ptr [rcx+1Ch], 1
0x18001e655  jz      short loc_18001E680
0x18001e657  lea     rax, [rbp+110h+pExceptionObject]
0x18001e65b  mov     [rsp+210h+var_1E8], rax
0x18001e660  lea     rax, [rbp+110h+var_B0]
0x18001e664  mov     [rsp+210h+var_1F0], rax
0x18001e669  lea     r9, [rbp+110h+sz]
0x18001e670  mov     rcx, [rcx+10h]
0x18001e674  call    WPP_SF_SSS
0x18001e679  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e680  cmp     rcx, r12
0x18001e683  jz      short loc_18001E6BE
0x18001e685  test    byte ptr [rcx+1Ch], 1
0x18001e689  jz      short loc_18001E6BE
0x18001e68b  lea     r9, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18001e692  mov     rax, r9
0x18001e695  test    rbx, rbx
0x18001e698  cmovnz  rax, rbx
0x18001e69c  test    rdi, rdi
0x18001e69f  cmovnz  r9, rdi
0x18001e6a3  mov     edx, 0Dh
0x18001e6a8  mov     [rsp+210h+var_1F0], rax
0x18001e6ad  lea     r8, WPP_03e33dbf1b4032e614116b7bba0efbaf_Traceguids
0x18001e6b4  mov     rcx, [rcx+10h]
0x18001e6b8  call    WPP_SF_SS
0x18001e6bd  nop
0x18001e6be  mov     rcx, rbx; void *
0x18001e6c1  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001e6c6  nop
0x18001e6c7  mov     rcx, rdi; void *
0x18001e6ca  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001e6cf  nop
0x18001e6d0  mov     rcx, [rsp+210h+var_1D0]; void *
0x18001e6d5  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001e6da  nop
0x18001e6db  mov     rcx, [rsp+210h+var_1C0]; void *
0x18001e6e0  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001e6e5  nop
0x18001e6e6  mov     rcx, [rsp+210h+rguid]; void *
0x18001e6eb  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001e6f0  mov     eax, [rbp+110h+var_188]
0x18001e6f3  mov     [rbp+110h+var_118], eax
0x18001e6f6  lea     rax, ??_7EapException@EapHost@@6B@; const EapHost::EapException::`vftable'
0x18001e6fd  mov     qword ptr [rbp+110h+pExceptionObject], rax
0x18001e701  lea     rdx, [rbp+110h+var_180]; struct EapHost::EapError *
0x18001e705  lea     rcx, [rbp+110h+var_110]; this
0x18001e709  call    ??0EapError@EapHost@@QEAA@AEBV01@@Z; EapHost::EapError::EapError(EapHost::EapError const &)
0x18001e70e  nop
0x18001e70f  lea     rdx, _TI3?AVEapException@EapHost@@; pThrowInfo
0x18001e716  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x18001e71a  call    _CxxThrowException_0
```
