# CFLACSource::read_callback(uchar * const,unsigned __int64 *)

- ea: `0x180027970`
- end: `0x180027b79`
- name: `?read_callback@CFLACSource@@UEAA?AW4FLAC__StreamDecoderReadStatus@@QEAEPEA_K@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, void *, const rsize_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001c638`
- `0x1800234fc`
- `0x180027970`
- `0x180027b80`
- `0x180027dcc`
- `0x180027df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027a5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027a5f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027a3e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027ab0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027a3e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180027ab0`
- `MFPlat!MFPutWorkItem` at `0x180027a4f`
- `MFPlat!MFPutWorkItem` at `0x180027a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::read_callback(__int64 a1, void *a2, const rsize_t *a3)
{
  CBuffReader *v6; // r14
  __int64 v7; // rdx
  unsigned int v8; // esi
  const void *v9; // rbp
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // ebx

  if ( !a2 || !*a3 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v12 = 88;
      goto LABEL_27;
    }
    return 2;
  }
  v6 = (CBuffReader *)(a1 + 216);
  v7 = *(unsigned int *)(a1 + 232);
  v8 = *(_DWORD *)(a1 + 236) - v7;
  v9 = (const void *)(v7 + *(_QWORD *)(a1 + 216));
  if ( !v9 || !v8 )
  {
    v10 = 1;
    if ( (*(_BYTE *)(a1 + 278) & 1) == 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
LABEL_9:
        *a3 = 0;
        return v10;
      }
      v11 = 89;
LABEL_8:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), v11, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
      goto LABEL_9;
    }
    if ( (int)CBuffReader::Reserve((CBuffReader *)(a1 + 216), *(_DWORD *)(a1 + 176)) < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
        v12 = 90;
LABEL_27:
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
        return 2;
      }
      return 2;
    }
    ResetEvent(*(HANDLE *)(a1 + 288));
    MFPutWorkItem(5u, (IMFAsyncCallback *)(a1 + 48), 0);
    if ( !WaitForSingleObject(*(HANDLE *)(a1 + 288), 0xFFFFFFFF) )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 92, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
      v13 = *(unsigned int *)(a1 + 232);
      v9 = (const void *)(v13 + *(_QWORD *)v6);
      if ( !v9 || (v8 = *(_DWORD *)(a1 + 236) - v13) == 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
          goto LABEL_9;
        v11 = 93;
        goto LABEL_8;
      }
      ResetEvent(*(HANDLE *)(a1 + 288));
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 94, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
    }
  }
  v14 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 >= v8 )
    v14 = v8;
  v15 = v14;
  v10 = memcpy_s(a2, *a3, v9, v14) != 0 ? 2 : 0;
  CBuffReader::MoveStart(v6, v15);
  return v10;
}

```

## disassembly

```asm
0x180027970  mov     [rsp+arg_8], rbx
0x180027975  mov     [rsp+arg_10], rbp
0x18002797a  push    rsi
0x18002797b  push    rdi
0x18002797c  push    r12
0x18002797e  push    r14
0x180027980  push    r15
0x180027982  sub     rsp, 20h
0x180027986  mov     r15, r8
0x180027989  mov     r12, rdx
0x18002798c  mov     rbx, rcx
0x18002798f  lea     rax, [rcx-70h]
0x180027993  mov     [rsp+48h+arg_0], rax
0x180027998  test    rdx, rdx
0x18002799b  jz      loc_180027B2F
0x1800279a1  cmp     qword ptr [r8], 0
0x1800279a5  jz      loc_180027B2F
0x1800279ab  lea     r14, [rcx+0D8h]
0x1800279b2  mov     edx, [r14+10h]
0x1800279b6  mov     esi, [r14+14h]
0x1800279ba  sub     esi, edx
0x1800279bc  mov     rbp, [r14]
0x1800279bf  add     rbp, rdx
0x1800279c2  jz      short loc_1800279CC
0x1800279c4  test    esi, esi
0x1800279c6  jnz     loc_180027ADE
0x1800279cc  mov     edi, 1
0x1800279d1  test    [rcx+116h], dil
0x1800279d8  jnz     short loc_180027A0D
0x1800279da  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800279df  cmp     al, dil
0x1800279e2  jb      short loc_180027A01
0x1800279e4  lea     edx, [rdi+58h]
0x1800279e7  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800279ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279f5  mov     rcx, [rcx+0D8h]
0x1800279fc  call    WPP_SF_
0x180027a01  mov     qword ptr [r15], 0
0x180027a08  jmp     loc_180027B60
0x180027a0d  mov     edx, [rcx+0B0h]; unsigned int
0x180027a13  mov     rcx, r14; this
0x180027a16  call    ?Reserve@CBuffReader@@QEAAJK@Z; CBuffReader::Reserve(ulong)
0x180027a1b  test    eax, eax
0x180027a1d  jns     short loc_180027A37
0x180027a1f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027a24  cmp     al, dil
0x180027a27  jb      loc_180027B5B
0x180027a2d  mov     edx, 5Ah ; 'Z'
0x180027a32  jmp     loc_180027B41
0x180027a37  mov     rcx, [rbx+120h]; hEvent
0x180027a3e  call    cs:__imp_ResetEvent
0x180027a44  lea     rdx, [rbx+30h]; pCallback
0x180027a48  xor     r8d, r8d; pState
0x180027a4b  lea     ecx, [r8+5]; dwQueue
0x180027a4f  call    cs:__imp_MFPutWorkItem
0x180027a55  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180027a58  mov     rcx, [rbx+120h]; hHandle
0x180027a5f  call    cs:__imp_WaitForSingleObject
0x180027a65  test    eax, eax
0x180027a67  jnz     short loc_180027ADE
0x180027a69  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027a6e  cmp     al, 4
0x180027a70  jb      short loc_180027A91
0x180027a72  mov     edx, 5Ch ; '\'
0x180027a77  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180027a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a85  mov     rcx, [rcx+0D8h]
0x180027a8c  call    WPP_SF_
0x180027a91  mov     ecx, [rbx+0E8h]
0x180027a97  mov     rbp, [r14]
0x180027a9a  add     rbp, rcx
0x180027a9d  jz      short loc_180027B17
0x180027a9f  mov     esi, [rbx+0ECh]
0x180027aa5  sub     esi, ecx
0x180027aa7  jz      short loc_180027B17
0x180027aa9  mov     rcx, [rbx+120h]; hEvent
0x180027ab0  call    cs:__imp_ResetEvent
0x180027ab6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027abb  cmp     al, 4
0x180027abd  jb      short loc_180027ADE
0x180027abf  mov     edx, 5Eh ; '^'
0x180027ac4  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180027acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ad2  mov     rcx, [rcx+0D8h]
0x180027ad9  call    WPP_SF_
0x180027ade  mov     eax, [r15]
0x180027ae1  cmp     eax, esi
0x180027ae3  cmovnb  eax, esi
0x180027ae6  mov     ebx, eax
0x180027ae8  mov     r9d, eax; SourceSize
0x180027aeb  mov     r8, rbp; Source
0x180027aee  mov     rdx, [r15]; DestinationSize
0x180027af1  mov     rcx, r12; Destination
0x180027af4  call    memcpy_s
0x180027af9  xor     r8d, r8d
0x180027afc  sub     r8d, eax
0x180027aff  neg     r8d
0x180027b02  sbb     eax, eax
0x180027b04  mov     edi, 2
0x180027b09  and     edi, eax
0x180027b0b  mov     edx, ebx; unsigned int
0x180027b0d  mov     rcx, r14; this
0x180027b10  call    ?MoveStart@CBuffReader@@QEAAJK@Z; CBuffReader::MoveStart(ulong)
0x180027b15  jmp     short loc_180027B60
0x180027b17  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027b1c  cmp     al, dil
0x180027b1f  jb      loc_180027A01
0x180027b25  mov     edx, 5Dh ; ']'
0x180027b2a  jmp     loc_1800279E7
0x180027b2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180027b34  mov     edi, 1
0x180027b39  cmp     al, dil
0x180027b3c  jb      short loc_180027B5B
0x180027b3e  lea     edx, [rdi+57h]
0x180027b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b48  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180027b4f  mov     rcx, [rcx+0D8h]
0x180027b56  call    WPP_SF_
0x180027b5b  mov     edi, 2
0x180027b60  mov     eax, edi
0x180027b62  mov     rbx, [rsp+48h+arg_8]
0x180027b67  mov     rbp, [rsp+48h+arg_10]
0x180027b6c  add     rsp, 20h
0x180027b70  pop     r15
0x180027b72  pop     r14
0x180027b74  pop     r12
0x180027b76  pop     rdi
0x180027b77  pop     rsi
0x180027b78  retn
```
