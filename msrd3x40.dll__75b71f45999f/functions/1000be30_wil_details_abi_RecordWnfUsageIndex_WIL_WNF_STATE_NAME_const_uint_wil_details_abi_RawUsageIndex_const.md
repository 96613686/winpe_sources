# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,uint,wil::details_abi::RawUsageIndex const &)

- ea: `0x1000be30`
- end: `0x1000c163`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YGXPBU__WIL__WNF_STATE_NAME@@IABVRawUsageIndex@12@@Z`
- size: `819`
- prototype: `void(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned int, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x1000c260`

## callees

- `0x10008d60`
- `0x1000a130`
- `0x1000aff0`
- `0x1000b0e0`
- `0x1000be30`
- `0x1000c170`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f490`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000bf57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000bf57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000bf46`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000bf46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c0ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c0ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c0f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c13d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c0f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c13d`

## string_xrefs

- `0x1000bf41`: `ntdll.dll`

## pseudocode

```c
void __userpurge wil::details_abi::RecordWnfUsageIndex(
        int a1@<edx>,
        char *a2@<ecx>,
        int a3@<ebp>,
        int a4@<edi>,
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a6,
        unsigned int a7,
        const struct wil::details_abi::RawUsageIndex *a8)
{
  void *v8; // esp
  char *v9; // edi
  wil::details_abi *v10; // eax
  int v11; // esi
  char v12; // dh
  char v13; // dl
  __int16 v14; // cx
  int v15; // eax
  FARPROC NtQueryWnfStateData; // esi
  HMODULE ModuleHandleW; // eax
  unsigned int v18; // eax
  int v19; // esi
  char v20; // cl
  int updated; // eax
  unsigned int v22; // esi
  void *v23; // eax
  HANDLE ProcessHeap; // eax
  void *v25; // eax
  HANDLE v26; // eax
  int v27; // [esp-40h] [ebp-10D0h]
  int v28; // [esp-3Ch] [ebp-10CCh]
  int v29; // [esp-3Ch] [ebp-10CCh]
  void *v30; // [esp-34h] [ebp-10C4h]
  void *v31; // [esp-34h] [ebp-10C4h]
  wil::details *v32; // [esp-30h] [ebp-10C0h]
  int v33; // [esp-2Ch] [ebp-10BCh]
  int v34; // [esp-24h] [ebp-10B4h] BYREF
  _DWORD v35[17]; // [esp-1Ch] [ebp-10ACh] BYREF
  unsigned int v36; // [esp+28h] [ebp-1068h]
  _WORD v37[2]; // [esp+2Ch] [ebp-1064h] BYREF
  char v38; // [esp+30h] [ebp-1060h]
  __int16 v39; // [esp+32h] [ebp-105Eh]
  char v40; // [esp+34h] [ebp-105Ch]
  int v41; // [esp+38h] [ebp-1058h]
  __int128 v42; // [esp+3Ch] [ebp-1054h]
  __int16 v43; // [esp+4Ch] [ebp-1044h]
  char v44; // [esp+4Eh] [ebp-1042h]
  wil::details_abi *v45; // [esp+50h] [ebp-1040h]
  int v46; // [esp+54h] [ebp-103Ch] BYREF
  int v47; // [esp+58h] [ebp-1038h] BYREF
  int v48; // [esp+5Ch] [ebp-1034h] BYREF
  unsigned int v49; // [esp+60h] [ebp-1030h]
  int v50; // [esp+64h] [ebp-102Ch] BYREF
  char v51; // [esp+6Bh] [ebp-1025h]
  _DWORD v52[1029]; // [esp+6Ch] [ebp-1024h] BYREF
  int v53; // [esp+1080h] [ebp-10h]
  int v54; // [esp+1084h] [ebp-Ch]
  void *v55; // [esp+1088h] [ebp-8h]
  int v56; // [esp+108Ch] [ebp-4h] BYREF
  void *retaddr; // [esp+1090h] [ebp+0h]

  v54 = a3;
  v55 = retaddr;
  v53 = -1;
  v52[1028] = &loc_1005F740;
  v52[1027] = NtCurrentTeb()->NtTib.ExceptionList;
  v52[1026] = &v56;
  v8 = alloca(4248);
  v33 = a4;
  v9 = a2;
  v10 = this;
  v45 = this;
  v36 = (unsigned int)&a2[8 * a1];
  v49 = 0;
  v46 = 0;
  while ( 1 )
  {
    v11 = *((unsigned __int16 *)v10 + 3);
    v12 = *((_BYTE *)v10 + 8);
    v13 = *((_BYTE *)v10 + 4);
    v14 = *((_WORD *)v10 + 1);
    v37[0] = *(_WORD *)v10;
    v37[1] = v14;
    v38 = v13;
    v39 = v11;
    v40 = v12;
    if ( (_WORD)v11 )
    {
      v15 = v11;
      if ( v12 == 1 )
      {
        v41 = v11 + 2;
      }
      else
      {
        if ( v12 == 2 )
          v15 = v11 + 4;
        v41 = v15;
      }
    }
    else
    {
      v41 = 0;
    }
    v43 = 0;
    v42 = 0;
    v44 = 0;
    v53 = 0;
    NtQueryWnfStateData = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v50 = 4096;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    NtQueryWnfStateData = GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
    g_wil_details_pfnNtQueryWnfStateData = (int (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))NtQueryWnfStateData;
    if ( NtQueryWnfStateData )
    {
LABEL_14:
      v19 = ((int (__thiscall *)(FARPROC, char *, _DWORD, _DWORD, int *, _DWORD *, int *))NtQueryWnfStateData)(
              NtQueryWnfStateData,
              v9,
              0,
              0,
              &v48,
              v52,
              &v50);
      wil::details::NtStatusToHr(v32, v33);
      if ( v19 )
      {
        v18 = 0;
        v50 = 0;
        v48 = 0;
      }
      else
      {
        v18 = v50;
      }
    }
    else
    {
      wil::details::NtStatusToHr(v32, v33);
      v18 = 0;
      v50 = 0;
      v48 = 0;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v37, v52, v18, 0x1000u);
    if ( HIBYTE(v43) )
      break;
    v35[1] = &v47;
    v35[2] = &v46;
    v35[3] = v37;
    v35[14] = v35;
    v47 = 0;
    v35[0] = &wistd::__function::__func<_lambda_4b29d149b8821cfbae4eba16ce6a2849_,bool __stdcall (void *,unsigned int,void *,unsigned int,unsigned int)>::`vftable';
    v20 = wil::details_abi::RawUsageIndex::Iterate(v45, &v34);
    v51 = v20;
    if ( !(_BYTE)v43 )
      goto LABEL_24;
    updated = wil_details_NtUpdateWnfStateData(v9, v42, DWORD1(v42) - v42, v27, v28, v48, 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData(v9, v42, DWORD1(v42) - v42, v27, v29, 0, 0);
      v20 = v51;
LABEL_24:
      v9 += 8;
      v22 = v49;
      v46 = v47;
      goto LABEL_25;
    }
    v22 = v49 + 1;
    v20 = 0;
    ++v49;
    v51 = 0;
LABEL_25:
    v53 = -1;
    v23 = (void *)HIDWORD(v42);
    HIDWORD(v42) = 0;
    if ( v23 )
    {
      v30 = v23;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v30);
      v20 = v51;
    }
    if ( !v20 && (unsigned int)v9 < v36 )
    {
      v10 = v45;
      if ( v22 < 0x32 )
        continue;
    }
    return;
  }
  v25 = (void *)HIDWORD(v42);
  HIDWORD(v42) = 0;
  if ( v25 )
  {
    v31 = v25;
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v31);
  }
}

```

## disassembly

```asm
0x1000be30  mov     edi, edi
0x1000be32  push    ebx
0x1000be33  mov     ebx, esp
0x1000be35  sub     esp, 8
0x1000be38  and     esp, 0FFFFFFF8h
0x1000be3b  add     esp, 4
0x1000be3e  push    ebp
0x1000be3f  mov     ebp, [ebx+4]
0x1000be42  mov     [esp+0Ch+var_8], ebp
0x1000be46  mov     ebp, esp
0x1000be48  push    0FFFFFFFFh
0x1000be4a  push    offset loc_1005F740
0x1000be4f  mov     eax, large fs:0
0x1000be55  push    eax
0x1000be56  push    ebx
0x1000be57  mov     eax, 1098h
0x1000be5c  call    __chkstk
0x1000be61  mov     eax, ___security_cookie
0x1000be66  xor     eax, ebp
0x1000be68  mov     [ebp-14h], eax
0x1000be6b  push    esi
0x1000be6c  push    edi; int
0x1000be6d  push    eax; this
0x1000be6e  lea     eax, [ebp-0Ch]
0x1000be71  mov     large fs:0, eax
0x1000be77  mov     edi, ecx
0x1000be79  mov     eax, [ebx+8]
0x1000be7c  lea     ecx, [edi+edx*8]
0x1000be7f  mov     [ebp-1034h], eax
0x1000be85  mov     [ebp-105Ch], ecx
0x1000be8b  mov     dword ptr [ebp-1024h], 0
0x1000be95  mov     dword ptr [ebp-1030h], 0
0x1000be9f  nop
0x1000bea0  movzx   esi, word ptr [eax+6]
0x1000bea4  mov     dh, [eax+8]
0x1000bea7  mov     dl, [eax+4]
0x1000beaa  movzx   ecx, word ptr [eax+2]
0x1000beae  mov     ax, [eax]
0x1000beb1  mov     [ebp-1058h], ax
0x1000beb8  mov     [ebp-1056h], cx
0x1000bebf  mov     [ebp-1054h], dl
0x1000bec5  mov     [ebp-1052h], si
0x1000becc  mov     [ebp-1050h], dh
0x1000bed2  test    si, si
0x1000bed5  jz      short loc_1000BEF9
0x1000bed7  mov     eax, esi
0x1000bed9  cmp     dh, 1
0x1000bedc  jnz     short loc_1000BEE9
0x1000bede  add     eax, 2
0x1000bee1  mov     [ebp-104Ch], eax
0x1000bee7  jmp     short loc_1000BF03
0x1000bee9  cmp     dh, 2
0x1000beec  jnz     short loc_1000BEF1
0x1000beee  add     eax, 4
0x1000bef1  mov     [ebp-104Ch], eax
0x1000bef7  jmp     short loc_1000BF03
0x1000bef9  mov     dword ptr [ebp-104Ch], 0
0x1000bf03  xorps   xmm0, xmm0
0x1000bf06  mov     word ptr [ebp-1038h], 0
0x1000bf0f  movups  xmmword ptr [ebp-1048h], xmm0
0x1000bf16  mov     byte ptr [ebp-1036h], 0
0x1000bf1d  mov     dword ptr [ebp-4], 0
0x1000bf24  mov     esi, _g_wil_details_pfnNtQueryWnfStateData
0x1000bf2a  mov     dword ptr [ebp-1020h], 1000h
0x1000bf34  test    esi, esi
0x1000bf36  jnz     short loc_1000BF83
0x1000bf38  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000bf3d  test    eax, eax
0x1000bf3f  jnz     short loc_1000BF51
0x1000bf41  push    offset ModuleName; "ntdll.dll"
0x1000bf46  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000bf4c  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000bf51  push    offset aNtquerywnfstat; "NtQueryWnfStateData"
0x1000bf56  push    eax; hModule
0x1000bf57  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000bf5d  mov     esi, eax
0x1000bf5f  mov     _g_wil_details_pfnNtQueryWnfStateData, esi
0x1000bf65  test    esi, esi
0x1000bf67  jnz     short loc_1000BF83
0x1000bf69  mov     ecx, 0C0000139h
0x1000bf6e  call    ?NtStatusToHr@details@wil@@YGJJ@Z; wil::details::NtStatusToHr(long)
0x1000bf73  xor     eax, eax
0x1000bf75  mov     [ebp-1020h], eax
0x1000bf7b  mov     [ebp-1028h], eax
0x1000bf81  jmp     short loc_1000BFCA
0x1000bf83  lea     eax, [ebp-1020h]
0x1000bf89  mov     ecx, esi
0x1000bf8b  push    eax
0x1000bf8c  lea     eax, [ebp-1018h]
0x1000bf92  push    eax
0x1000bf93  lea     eax, [ebp-1028h]
0x1000bf99  push    eax
0x1000bf9a  push    0; int
0x1000bf9c  push    0; unsigned int
0x1000bf9e  push    edi; void *
0x1000bf9f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000bfa5  call    esi ; _g_wil_details_pfnNtQueryWnfStateData
0x1000bfa7  mov     esi, eax
0x1000bfa9  mov     ecx, esi
0x1000bfab  call    ?NtStatusToHr@details@wil@@YGJJ@Z; wil::details::NtStatusToHr(long)
0x1000bfb0  test    esi, esi
0x1000bfb2  jz      short loc_1000BFC4
0x1000bfb4  xor     eax, eax
0x1000bfb6  mov     [ebp-1020h], eax
0x1000bfbc  mov     [ebp-1028h], eax
0x1000bfc2  jmp     short loc_1000BFCA
0x1000bfc4  mov     eax, [ebp-1020h]
0x1000bfca  push    1000h; unsigned int
0x1000bfcf  push    eax; unsigned int
0x1000bfd0  lea     eax, [ebp-1018h]
0x1000bfd6  push    eax; int
0x1000bfd7  lea     ecx, [ebp-1058h]; this
0x1000bfdd  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QAEXPAXII@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,uint,uint)
0x1000bfe2  cmp     byte ptr [ebp-1037h], 0
0x1000bfe9  jnz     loc_1000C11F
0x1000bfef  mov     ecx, [ebp-1034h]
0x1000bff5  lea     eax, [ebp-102Ch]
0x1000bffb  mov     [ebp-109Ch], eax
0x1000c001  lea     eax, [ebp-1030h]
0x1000c007  mov     [ebp-1098h], eax
0x1000c00d  lea     eax, [ebp-1058h]
0x1000c013  mov     [ebp-1094h], eax
0x1000c019  lea     eax, [ebp-10A0h]
0x1000c01f  mov     [ebp-1068h], eax
0x1000c025  lea     eax, [ebp-10A8h]
0x1000c02b  push    eax
0x1000c02c  mov     dword ptr [ebp-102Ch], 0
0x1000c036  mov     dword ptr [ebp-10A0h], offset ??_7?$__func@V_lambda_4b29d149b8821cfbae4eba16ce6a2849_@@$$A6G_NPAXI0II@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_4b29d149b8821cfbae4eba16ce6a2849_,bool (void *,uint,void *,uint,uint)>::`vftable'
0x1000c040  call    ?Iterate@RawUsageIndex@details_abi@wil@@QBE_NV?$function@$$A6G_NPAXI0II@Z@wistd@@@Z; wil::details_abi::RawUsageIndex::Iterate(wistd::function<bool (void *,uint,void *,uint,uint)>)
0x1000c045  cmp     byte ptr [ebp-1038h], 0
0x1000c04c  mov     cl, al
0x1000c04e  mov     [ebp-1019h], cl
0x1000c054  jz      short loc_1000C0BC
0x1000c056  mov     ecx, [ebp-1044h]
0x1000c05c  mov     edx, [ebp-1048h]; unsigned int
0x1000c062  sub     ecx, edx
0x1000c064  push    1; int
0x1000c066  push    dword ptr [ebp-1028h]; int
0x1000c06c  sub     esp, 8
0x1000c06f  push    ecx; int
0x1000c070  mov     ecx, edi; void *
0x1000c072  call    _wil_details_NtUpdateWnfStateData@28; wil_details_NtUpdateWnfStateData(x,x,x,x,x,x,x)
0x1000c077  cmp     eax, 0C0000001h
0x1000c07c  jnz     short loc_1000C095
0x1000c07e  mov     esi, [ebp-1024h]
0x1000c084  inc     esi
0x1000c085  xor     cl, cl
0x1000c087  mov     [ebp-1024h], esi
0x1000c08d  mov     [ebp-1019h], cl
0x1000c093  jmp     short loc_1000C0D1
0x1000c095  test    eax, eax
0x1000c097  jz      short loc_1000C0B6
0x1000c099  mov     eax, [ebp-1044h]
0x1000c09f  mov     ecx, edi; void *
0x1000c0a1  mov     edx, [ebp-1048h]; unsigned int
0x1000c0a7  sub     eax, edx
0x1000c0a9  push    0; int
0x1000c0ab  push    0; int
0x1000c0ad  sub     esp, 8
0x1000c0b0  push    eax; int
0x1000c0b1  call    _wil_details_NtUpdateWnfStateData@28; wil_details_NtUpdateWnfStateData(x,x,x,x,x,x,x)
0x1000c0b6  mov     cl, [ebp-1019h]
0x1000c0bc  mov     eax, [ebp-102Ch]
0x1000c0c2  add     edi, 8
0x1000c0c5  mov     esi, [ebp-1024h]
0x1000c0cb  mov     [ebp-1030h], eax
0x1000c0d1  mov     dword ptr [ebp-4], 0FFFFFFFFh
0x1000c0d8  mov     eax, [ebp-103Ch]
0x1000c0de  mov     dword ptr [ebp-103Ch], 0
0x1000c0e8  test    eax, eax
0x1000c0ea  jz      short loc_1000C102
0x1000c0ec  push    eax; lpMem
0x1000c0ed  push    0; dwFlags
0x1000c0ef  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000c0f5  push    eax; hHeap
0x1000c0f6  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000c0fc  mov     cl, [ebp-1019h]
0x1000c102  test    cl, cl
0x1000c104  jnz     short loc_1000C143
0x1000c106  cmp     edi, [ebp-105Ch]
0x1000c10c  jnb     short loc_1000C143
0x1000c10e  mov     eax, [ebp-1034h]
0x1000c114  cmp     esi, 32h ; '2'
0x1000c117  jb      loc_1000BEA0
0x1000c11d  jmp     short loc_1000C143
0x1000c11f  mov     eax, [ebp-103Ch]
0x1000c125  mov     dword ptr [ebp-103Ch], 0
0x1000c12f  test    eax, eax
0x1000c131  jz      short loc_1000C143
0x1000c133  push    eax; lpMem
0x1000c134  push    0; dwFlags
0x1000c136  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000c13c  push    eax; hHeap
0x1000c13d  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000c143  mov     ecx, [ebp-0Ch]
0x1000c146  mov     large fs:0, ecx
0x1000c14d  pop     ecx
0x1000c14e  pop     edi
0x1000c14f  pop     esi
0x1000c150  mov     ecx, [ebp-14h]
0x1000c153  xor     ecx, ebp; StackCookie
0x1000c155  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000c15a  mov     esp, ebp
0x1000c15c  pop     ebp
0x1000c15d  mov     esp, ebx
0x1000c15f  pop     ebx
0x1000c160  retn    4
0x1005f730  lea     ecx, [ebp-1058h]; this
0x1005f736  jmp     ??1RawUsageIndex@details_abi@wil@@QAE@XZ; wil::details_abi::RawUsageIndex::~RawUsageIndex(void)
0x1005f740  nop
0x1005f741  nop
0x1005f742  mov     edx, [esp+arg_4]
0x1005f746  lea     eax, [edx+0Ch]
0x1005f749  mov     ecx, [edx-10A8h]
0x1005f74f  xor     ecx, eax; StackCookie
0x1005f751  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f756  mov     ecx, [edx-8]
0x1005f759  xor     ecx, eax; StackCookie
0x1005f75b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f760  mov     eax, offset stru_10062B58
0x1005f765  jmp     ___CxxFrameHandler3
```
