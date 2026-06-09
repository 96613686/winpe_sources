# EapHost::EapException::Throw(EapHost::EapError const &)

- ea: `0x18001d9bc`
- end: `0x18001dc1e`
- name: `?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(const struct EapHost::EapError *)`
- caller_count: `17`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180017930`
- `0x180018020`
- `0x1800182d0`
- `0x1800183d0`
- `0x180018500`
- `0x180018740`
- `0x1800188c0`
- `0x1800189f0`
- `0x180018b20`
- `0x18001ac7c`
- `0x18001afa0`
- `0x18001cf70`
- `0x18001dc24`
- `0x18001dc64`
- `0x18001dcbc`
- `0x18001dd64`
- `0x180036bd2`

## callees

- `0x18000343c`
- `0x180004e7c`
- `0x1800052c0`
- `0x1800072cc`
- `0x18001ca1c`
- `0x18001d79c`
- `0x18001d8f0`
- `0x18001d9bc`
- `0x18001dde4`
- `0x18001df20`
- `0x18001eaf4`
- `0x18002fd44`
- `0x180033d54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db0f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db21`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db33`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db0f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db21`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001db33`

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
0x18001d9bc  mov     [rsp-8+arg_8], rbx
0x18001d9c1  mov     [rsp-8+arg_10], rsi
0x18001d9c6  push    rbp
0x18001d9c7  push    rdi
0x18001d9c8  push    r12
0x18001d9ca  lea     rbp, [rsp-100h]
0x18001d9d2  sub     rsp, 200h
0x18001d9d9  mov     rdi, rcx
0x18001d9dc  xor     esi, esi
0x18001d9de  mov     dword ptr [rsp+210h+var_1E0], esi
0x18001d9e2  mov     rdx, rcx; struct EapHost::EapError *
0x18001d9e5  lea     rcx, [rbp+110h+var_190]; this
0x18001d9e9  call    ??0EapException@EapHost@@QEAA@AEBVEapError@1@@Z; EapHost::EapException::EapException(EapHost::EapError const &)
0x18001d9ee  nop
0x18001d9ef  mov     rax, cs:WPP_GLOBAL_Control
0x18001d9f6  test    byte ptr [rax+1Ch], 1
0x18001d9fa  jz      loc_18001DBEE
0x18001da00  mov     [rsp+210h+rguid], rsi
0x18001da05  mov     [rsp+210h+var_1A8], rsi
0x18001da0a  mov     [rsp+210h+var_1C0], rsi
0x18001da0f  mov     [rsp+210h+var_1B8], rsi
0x18001da14  mov     [rsp+210h+var_1D0], rsi
0x18001da19  mov     [rsp+210h+var_1C8], rsi
0x18001da1e  mov     [rsp+210h+var_1E0], rsi
0x18001da23  mov     [rsp+210h+var_1D8], rsi
0x18001da28  lea     r8, [rdi+18h]
0x18001da2c  lea     ebx, [rsi+10h]
0x18001da2f  mov     edx, ebx
0x18001da31  lea     rcx, [rsp+210h+rguid]
0x18001da36  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001da3b  lea     r8, [rdi+28h]
0x18001da3f  mov     edx, ebx
0x18001da41  lea     rcx, [rsp+210h+var_1C0]
0x18001da46  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001da4b  lea     r8, [rdi+38h]
0x18001da4f  mov     edx, ebx
0x18001da51  lea     rcx, [rsp+210h+var_1D0]
0x18001da56  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001da5b  mov     rdx, [rdi+48h]
0x18001da5f  lea     rcx, [rsp+210h+var_1E0]
0x18001da64  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001da69  mov     rdx, [rdi+50h]
0x18001da6d  lea     rcx, [rsp+210h+var_1D8]
0x18001da72  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001da77  lea     r12, WPP_GLOBAL_Control
0x18001da7e  mov     rax, cs:WPP_GLOBAL_Control
0x18001da85  cmp     rax, r12
0x18001da88  jz      short loc_18001DAC7
0x18001da8a  test    byte ptr [rax+1Ch], 1
0x18001da8e  jz      short loc_18001DAC7
0x18001da90  mov     ebx, [rdi+14h]
0x18001da93  lea     rdx, [rsp+210h+var_1A0]
0x18001da98  mov     rcx, rdi
0x18001da9b  call    ?GetEapType@EapError@EapHost@@QEBA?AV?$unique_ptr@VEapMethodType@EapHost@@U?$default_delete@VEapMethodType@EapHost@@@std@@@std@@XZ; EapHost::EapError::GetEapType(void)
0x18001daa0  mov     esi, 1
0x18001daa5  mov     rax, [rax]
0x18001daa8  movzx   ecx, byte ptr [rax+8]
0x18001daac  mov     dword ptr [rsp+210h+var_1E8], ebx
0x18001dab0  mov     dword ptr [rsp+210h+var_1F0], ecx
0x18001dab4  mov     r9d, [rdi]
0x18001dab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dabe  mov     rcx, [rcx+10h]
0x18001dac2  call    WPP_SF_DDD
0x18001dac7  test    sil, 1
0x18001dacb  jz      short loc_18001DAD7
0x18001dacd  lea     rcx, [rsp+210h+var_1A0]
0x18001dad2  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x18001dad7  mov     ebx, 4Eh ; 'N'
0x18001dadc  mov     r8d, ebx; Size
0x18001dadf  xor     edx, edx; Val
0x18001dae1  lea     rcx, [rbp+110h+sz]; void *
0x18001dae8  call    memset_0
0x18001daed  mov     r8d, ebx; Size
0x18001daf0  xor     edx, edx; Val
0x18001daf2  lea     rcx, [rbp+110h+var_B0]; void *
0x18001daf6  call    memset_0
0x18001dafb  mov     ebx, 27h ; '''
0x18001db00  mov     r8d, ebx; cchMax
0x18001db03  lea     rdx, [rbp+110h+sz]; lpsz
0x18001db0a  mov     rcx, [rsp+210h+rguid]; rguid
0x18001db0f  call    cs:__imp_StringFromGUID2
0x18001db15  mov     r8d, ebx; cchMax
0x18001db18  lea     rdx, [rbp+110h+var_B0]; lpsz
0x18001db1c  mov     rcx, [rsp+210h+var_1C0]; rguid
0x18001db21  call    cs:__imp_StringFromGUID2
0x18001db27  mov     r8d, ebx; cchMax
0x18001db2a  lea     rdx, [rbp+110h+pExceptionObject]; lpsz
0x18001db2e  mov     rcx, [rsp+210h+var_1D0]; rguid
0x18001db33  call    cs:__imp_StringFromGUID2
0x18001db39  mov     rdi, [rsp+210h+var_1E0]
0x18001db3e  mov     rbx, [rsp+210h+var_1D8]
0x18001db43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db4a  cmp     rcx, r12
0x18001db4d  jz      short loc_18001DBBC
0x18001db4f  test    byte ptr [rcx+1Ch], 1
0x18001db53  jz      short loc_18001DB7E
0x18001db55  lea     rax, [rbp+110h+pExceptionObject]
0x18001db59  mov     [rsp+210h+var_1E8], rax
0x18001db5e  lea     rax, [rbp+110h+var_B0]
0x18001db62  mov     [rsp+210h+var_1F0], rax
0x18001db67  lea     r9, [rbp+110h+sz]
0x18001db6e  mov     rcx, [rcx+10h]
0x18001db72  call    WPP_SF_SSS
0x18001db77  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db7e  cmp     rcx, r12
0x18001db81  jz      short loc_18001DBBC
0x18001db83  test    byte ptr [rcx+1Ch], 1
0x18001db87  jz      short loc_18001DBBC
0x18001db89  lea     r9, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18001db90  mov     rax, r9
0x18001db93  test    rbx, rbx
0x18001db96  cmovnz  rax, rbx
0x18001db9a  test    rdi, rdi
0x18001db9d  cmovnz  r9, rdi
0x18001dba1  mov     edx, 0Dh
0x18001dba6  mov     [rsp+210h+var_1F0], rax
0x18001dbab  lea     r8, WPP_03e33dbf1b4032e614116b7bba0efbaf_Traceguids
0x18001dbb2  mov     rcx, [rcx+10h]
0x18001dbb6  call    WPP_SF_SS
0x18001dbbb  nop
0x18001dbbc  mov     rcx, rbx; void *
0x18001dbbf  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001dbc4  nop
0x18001dbc5  mov     rcx, rdi; void *
0x18001dbc8  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001dbcd  nop
0x18001dbce  mov     rcx, [rsp+210h+var_1D0]; void *
0x18001dbd3  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001dbd8  nop
0x18001dbd9  mov     rcx, [rsp+210h+var_1C0]; void *
0x18001dbde  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001dbe3  nop
0x18001dbe4  mov     rcx, [rsp+210h+rguid]; void *
0x18001dbe9  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18001dbee  mov     eax, [rbp+110h+var_188]
0x18001dbf1  mov     [rbp+110h+var_118], eax
0x18001dbf4  lea     rax, ??_7EapException@EapHost@@6B@; const EapHost::EapException::`vftable'
0x18001dbfb  mov     qword ptr [rbp+110h+pExceptionObject], rax
0x18001dbff  lea     rdx, [rbp+110h+var_180]; struct EapHost::EapError *
0x18001dc03  lea     rcx, [rbp+110h+var_110]; this
0x18001dc07  call    ??0EapError@EapHost@@QEAA@AEBV01@@Z; EapHost::EapError::EapError(EapHost::EapError const &)
0x18001dc0c  nop
0x18001dc0d  lea     rdx, _TI3?AVEapException@EapHost@@; pThrowInfo
0x18001dc14  lea     rcx, [rbp+110h+pExceptionObject]; pExceptionObject
0x18001dc18  call    _CxxThrowException_0
```
