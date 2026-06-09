# COfflineFilesCache::Encrypt(HWND__ *,int,ulong,int,IOfflineFilesSyncProgress *)

- ea: `0x18000d2e0`
- end: `0x18000d4fd`
- name: `?Encrypt@COfflineFilesCache@@UEAAJPEAUHWND__@@HKHPEAUIOfflineFilesSyncProgress@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(COfflineFilesCache *__hidden this, HWND, int, unsigned int, int, struct IOfflineFilesSyncProgress *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180006c00`
- `0x18000d198`
- `0x18000d2e0`
- `0x18000f0e4`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000d380`
- `OLEAUT32!__imp_VariantInit` at `0x18000d380`
- `OLEAUT32!__imp_VariantClear` at `0x18000d3a2`
- `OLEAUT32!__imp_VariantClear` at `0x18000d3a2`

## string_xrefs

- `0x18000d349`: `EncryptCache`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::Encrypt(
        COfflineFilesCache *this,
        HWND a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        struct IOfflineFilesSyncProgress *a6)
{
  __int64 v10; // r9
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // ebx
  COfflineFilesCache *v14; // rcx
  void *v15; // rdx
  void *v16; // [rsp+30h] [rbp-40h] BYREF
  struct IOfflineFilesService *v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  struct AsyncIOfflineFilesService *v19; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  int v21; // [rsp+A8h] [rbp+38h] BYREF

  v10 = a4 & 0xFFFEE1FF;
  if ( (_DWORD)v10 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_91a48976ead63973ddd357b80bae3284_Traceguids, v10);
    return 2147942487LL;
  }
  v12 = *(_QWORD *)this;
  v18 = 0;
  v21 = 0;
  if ( (*(int (__fastcall **)(COfflineFilesCache *, const wchar_t *, __int64 *))(v12 + 136))(
         this,
         L"EncryptCache",
         &v18) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    (*(void (__fastcall **)(__int64, VARIANTARG *, int *))(*(_QWORD *)v18 + 88LL))(v18, &pvarg, &v21);
    VariantClear(&pvarg);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( v21 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
    return 2147942405LL;
  }
  v17 = 0;
  v13 = CInterfaceInGITBase::_Unmarshal(
          (COfflineFilesCache *)((char *)this + 32),
          &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
          (void **)&v17);
  if ( v13 >= 0 )
  {
    v14 = (COfflineFilesCache *)a6;
    v15 = 0;
    v16 = 0;
    if ( a6 )
    {
      v13 = CSyncProgressAdapter::CreateInstance(a6, 0, &v16);
      if ( v13 < 0 )
      {
LABEL_23:
        (*(void (__fastcall **)(struct IOfflineFilesService *))(*(_QWORD *)v17 + 16LL))(v17);
        goto LABEL_24;
      }
      v15 = v16;
    }
    if ( a5 )
    {
      v19 = 0;
      v13 = COfflineFilesCache::_CreateAsyncServiceObject(v14, v17, &v19);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(struct AsyncIOfflineFilesService *, HWND, _QWORD, _QWORD, void *))(*(_QWORD *)v19 + 168LL))(
                v19,
                a2,
                a3,
                a4,
                v16);
        (*(void (__fastcall **)(struct AsyncIOfflineFilesService *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, HWND, _QWORD, _QWORD, void *))(*(_QWORD *)v17 + 96LL))(
              v17,
              a2,
              a3,
              a4,
              v15);
    }
    if ( v16 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_23;
  }
LABEL_24:
  result = 0;
  if ( v13 < 0 )
    return (unsigned int)v13;
  return result;
}

```

## disassembly

```asm
0x18000d2e0  mov     [rsp-18h+arg_0], rbx
0x18000d2e5  mov     [rsp-18h+arg_8], rsi
0x18000d2ea  push    rbp
0x18000d2eb  push    rdi
0x18000d2ec  push    r14
0x18000d2ee  mov     rbp, rsp
0x18000d2f1  sub     rsp, 70h
0x18000d2f5  mov     edi, r9d
0x18000d2f8  mov     esi, r8d
0x18000d2fb  mov     r14, rdx
0x18000d2fe  mov     rbx, rcx
0x18000d301  and     r9d, 0FFFEE1FFh
0x18000d308  jz      short loc_18000D342
0x18000d30a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d311  lea     rax, WPP_GLOBAL_Control
0x18000d318  cmp     rcx, rax
0x18000d31b  jz      short loc_18000D338
0x18000d31d  test    byte ptr [rcx+1Ch], 2
0x18000d321  jz      short loc_18000D338
0x18000d323  mov     rcx, [rcx+10h]
0x18000d327  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000d32e  mov     edx, 15h
0x18000d333  call    WPP_SF_d
0x18000d338  mov     eax, 80070057h
0x18000d33d  jmp     loc_18000D4E8
0x18000d342  mov     rax, [rcx]
0x18000d345  lea     r8, [rbp+var_30]
0x18000d349  lea     rdx, aEncryptcache; "EncryptCache"
0x18000d350  mov     [rbp+var_30], 0
0x18000d358  mov     [rbp+arg_18], 0
0x18000d35f  mov     rax, [rax+88h]
0x18000d366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d36b  test    eax, eax
0x18000d36d  js      short loc_18000D3B8
0x18000d36f  xorps   xmm0, xmm0
0x18000d372  lea     rcx, [rbp+pvarg]; pvarg
0x18000d376  xor     eax, eax
0x18000d378  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000d37c  mov     qword ptr [rbp+pvarg+10h], rax
0x18000d380  call    cs:__imp_VariantInit
0x18000d386  mov     rcx, [rbp+var_30]
0x18000d38a  lea     r8, [rbp+arg_18]
0x18000d38e  lea     rdx, [rbp+pvarg]
0x18000d392  mov     rax, [rcx]
0x18000d395  mov     rax, [rax+58h]
0x18000d399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d39e  lea     rcx, [rbp+pvarg]; pvarg
0x18000d3a2  call    cs:__imp_VariantClear
0x18000d3a8  mov     rcx, [rbp+var_30]
0x18000d3ac  mov     rax, [rcx]
0x18000d3af  mov     rax, [rax+10h]
0x18000d3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b8  cmp     [rbp+arg_18], 0
0x18000d3bc  jz      short loc_18000D3F6
0x18000d3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3c5  lea     rax, WPP_GLOBAL_Control
0x18000d3cc  cmp     rcx, rax
0x18000d3cf  jz      short loc_18000D3EC
0x18000d3d1  test    byte ptr [rcx+1Ch], 2
0x18000d3d5  jz      short loc_18000D3EC
0x18000d3d7  mov     rcx, [rcx+10h]
0x18000d3db  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000d3e2  mov     edx, 16h
0x18000d3e7  call    WPP_SF_
0x18000d3ec  mov     eax, 80070005h
0x18000d3f1  jmp     loc_18000D4E8
0x18000d3f6  lea     rcx, [rbx+20h]; this
0x18000d3fa  mov     [rbp+var_38], 0
0x18000d402  lea     r8, [rbp+var_38]; void **
0x18000d406  lea     rdx, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce; struct _GUID *
0x18000d40d  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x18000d412  mov     ebx, eax
0x18000d414  test    eax, eax
0x18000d416  js      loc_18000D4E1
0x18000d41c  mov     rcx, [rbp+arg_28]; struct IOfflineFilesSyncProgress *
0x18000d420  xor     edx, edx; struct _GUID *
0x18000d422  mov     [rbp+var_40], rdx
0x18000d426  test    rcx, rcx
0x18000d429  jz      short loc_18000D442
0x18000d42b  lea     r8, [rbp+var_40]; void **
0x18000d42f  call    ?CreateInstance@CSyncProgressAdapter@@SAJPEAUIOfflineFilesSyncProgress@@AEBU_GUID@@PEAPEAX@Z; CSyncProgressAdapter::CreateInstance(IOfflineFilesSyncProgress *,_GUID const &,void * *)
0x18000d434  mov     ebx, eax
0x18000d436  test    eax, eax
0x18000d438  js      loc_18000D4D1
0x18000d43e  mov     rdx, [rbp+var_40]
0x18000d442  cmp     [rbp+arg_20], 0
0x18000d446  jz      short loc_18000D49C
0x18000d448  mov     rdx, [rbp+var_38]; struct IOfflineFilesService *
0x18000d44c  lea     r8, [rbp+var_28]; struct AsyncIOfflineFilesService **
0x18000d450  mov     [rbp+var_28], 0
0x18000d458  call    ?_CreateAsyncServiceObject@COfflineFilesCache@@AEAAJPEAUIOfflineFilesService@@PEAPEAUAsyncIOfflineFilesService@@@Z; COfflineFilesCache::_CreateAsyncServiceObject(IOfflineFilesService *,AsyncIOfflineFilesService * *)
0x18000d45d  mov     ebx, eax
0x18000d45f  test    eax, eax
0x18000d461  js      short loc_18000D4BC
0x18000d463  mov     rdx, [rbp+var_40]
0x18000d467  mov     r9d, edi
0x18000d46a  mov     rcx, [rbp+var_28]
0x18000d46e  mov     r8d, esi
0x18000d471  mov     [rsp+70h+var_50], rdx
0x18000d476  mov     rdx, r14
0x18000d479  mov     rax, [rcx]
0x18000d47c  mov     rax, [rax+0A8h]
0x18000d483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d488  mov     rcx, [rbp+var_28]
0x18000d48c  mov     ebx, eax
0x18000d48e  mov     rax, [rcx]
0x18000d491  mov     rax, [rax+10h]
0x18000d495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d49a  jmp     short loc_18000D4BC
0x18000d49c  mov     rcx, [rbp+var_38]
0x18000d4a0  mov     r9d, edi
0x18000d4a3  mov     [rsp+70h+var_50], rdx
0x18000d4a8  mov     r8d, esi
0x18000d4ab  mov     rdx, r14
0x18000d4ae  mov     rax, [rcx]
0x18000d4b1  mov     rax, [rax+60h]
0x18000d4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4ba  mov     ebx, eax
0x18000d4bc  mov     rcx, [rbp+var_40]
0x18000d4c0  test    rcx, rcx
0x18000d4c3  jz      short loc_18000D4D1
0x18000d4c5  mov     rax, [rcx]
0x18000d4c8  mov     rax, [rax+10h]
0x18000d4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4d1  mov     rcx, [rbp+var_38]
0x18000d4d5  mov     rax, [rcx]
0x18000d4d8  mov     rax, [rax+10h]
0x18000d4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e1  xor     eax, eax
0x18000d4e3  test    ebx, ebx
0x18000d4e5  cmovs   eax, ebx
0x18000d4e8  lea     r11, [rsp+70h+var_s0]
0x18000d4ed  mov     rbx, [r11+20h]
0x18000d4f1  mov     rsi, [r11+28h]
0x18000d4f5  mov     rsp, r11
0x18000d4f8  pop     r14
0x18000d4fa  pop     rdi
0x18000d4fb  pop     rbp
0x18000d4fc  retn
```
