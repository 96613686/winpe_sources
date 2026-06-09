# ATL::CComObjectCached<DataStoreComServer>::CreateInstance(ATL::CComObjectCached<DataStoreComServer> * *)

- ea: `0x180003f78`
- end: `0x180004055`
- name: `?CreateInstance@?$CComObjectCached@VDataStoreComServer@@@ATL@@SAJPEAPEAV12@@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003ad0`

## callees

- `0x180002310`
- `0x180003f78`
- `0x18000433c`
- `0x1800067a8`
- `0x1800068dc`

## import_xrefs

- `msvcrt!free` at `0x18000403e`
- `msvcrt!free` at `0x18000403e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObjectCached<DataStoreComServer>::CreateInstance(DataStoreComServer **a1)
{
  DataStoreComServer **v1; // rsi
  unsigned int v3; // edi
  DataStoreComServer *v4; // rax
  DataStoreComServer *v5; // rbx
  int v6; // ecx
  int v7; // eax
  DataStoreComServer *v9; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (DataStoreComServer *)operator new(0x50u);
    v5 = v4;
    if ( v4 )
    {
      DataStoreComServer::DataStoreComServer(v4);
      *(_QWORD *)v5 = &ATL::CComObjectCached<DataStoreComServer>::`vftable';
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v5 + 16));
    if ( v6 >= 0 )
      *((_BYTE *)v5 + 56) = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    if ( v3 )
    {
      *(_QWORD *)v5 = &ATL::CComObjectCached<DataStoreComServer>::`vftable';
      *((_DWORD *)v5 + 2) = -1073741823;
      DataStoreComServer::~DataStoreComServer(v5);
      free(v5);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180003f78  mov     [rsp+arg_0], rcx
0x180003f7d  push    rbx
0x180003f7e  push    rsi
0x180003f7f  push    rdi
0x180003f80  push    r14
0x180003f82  sub     rsp, 28h
0x180003f86  mov     rsi, rcx
0x180003f89  test    rcx, rcx
0x180003f8c  jnz     short loc_180003F98
0x180003f8e  mov     eax, 80004003h
0x180003f93  jmp     loc_18000404B
0x180003f98  mov     qword ptr [rcx], 0
0x180003f9f  mov     edi, 8007000Eh
0x180003fa4  mov     [rsp+48h+arg_8], edi
0x180003fa8  mov     [rsp+48h+arg_10], 0
0x180003fb1  mov     ecx, 50h ; 'P'; Size
0x180003fb6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fbb  mov     rbx, rax
0x180003fbe  mov     [rsp+48h+arg_18], rax
0x180003fc3  test    rbx, rbx
0x180003fc6  jz      short loc_180003FDC
0x180003fc8  mov     rcx, rax; this
0x180003fcb  call    ??0DataStoreComServer@@QEAA@XZ; DataStoreComServer::DataStoreComServer(void)
0x180003fd0  lea     r14, ??_7?$CComObjectCached@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObjectCached<DataStoreComServer>::`vftable'
0x180003fd7  mov     [rbx], r14
0x180003fda  jmp     short loc_180003FE3
0x180003fdc  lea     r14, ??_7?$CComObjectCached@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObjectCached<DataStoreComServer>::`vftable'
0x180003fe3  mov     [rsp+48h+arg_10], rbx
0x180003fe8  jmp     short loc_180003FFF
0x180003fea  lea     r14, ??_7?$CComObjectCached@VDataStoreComServer@@@ATL@@6B@; const ATL::CComObjectCached<DataStoreComServer>::`vftable'
0x180003ff1  mov     rsi, [rsp+48h+arg_0]
0x180003ff6  mov     edi, [rsp+48h+arg_8]
0x180003ffa  mov     rbx, [rsp+48h+arg_10]
0x180003fff  test    rbx, rbx
0x180004002  jz      short loc_180004046
0x180004004  lea     rcx, [rbx+10h]; this
0x180004008  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000400d  mov     ecx, eax
0x18000400f  test    eax, eax
0x180004011  js      short loc_180004017
0x180004013  mov     byte ptr [rbx+38h], 1
0x180004017  xor     eax, eax
0x180004019  test    ecx, ecx
0x18000401b  cmovs   eax, ecx
0x18000401e  xor     edi, edi
0x180004020  test    eax, eax
0x180004022  cmovs   edi, eax
0x180004025  test    edi, edi
0x180004027  jz      short loc_180004046
0x180004029  mov     [rbx], r14
0x18000402c  mov     dword ptr [rbx+8], 0C0000001h
0x180004033  mov     rcx, rbx; this
0x180004036  call    ??1DataStoreComServer@@QEAA@XZ; DataStoreComServer::~DataStoreComServer(void)
0x18000403b  mov     rcx, rbx; Block
0x18000403e  call    cs:__imp_free
0x180004044  xor     ebx, ebx
0x180004046  mov     [rsi], rbx
0x180004049  mov     eax, edi
0x18000404b  add     rsp, 28h
0x18000404f  pop     r14
0x180004051  pop     rdi
0x180004052  pop     rsi
0x180004053  pop     rbx
0x180004054  retn
```
