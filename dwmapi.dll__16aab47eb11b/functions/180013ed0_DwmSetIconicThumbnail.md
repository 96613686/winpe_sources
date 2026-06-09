# DwmSetIconicThumbnail

- ea: `0x180013ed0`
- end: `0x18001417b`
- name: `DwmSetIconicThumbnail`
- size: `683`
- prototype: `HRESULT __stdcall(HWND hwnd, HBITMAP hbmp, DWORD dwSITFlags)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001520`
- `0x18000352c`
- `0x180008004`
- `0x180008ab4`
- `0x18000a5b4`
- `0x18000b8dc`
- `0x18000b990`
- `0x18000d0a0`
- `0x18000ddc4`
- `0x180013ed0`
- `0x180014af0`
- `0x180014b4c`
- `0x180015224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f4e`
- `USER32!GetWindowThreadProcessId` at `0x180013f48`
- `USER32!GetWindowThreadProcessId` at `0x180013f48`
- `USER32!GetShellWindow` at `0x180013f2d`
- `USER32!GetShellWindow` at `0x180013f2d`
- `GDI32!GetObjectW` at `0x180013f9d`
- `GDI32!GetObjectW` at `0x180013f9d`

## pseudocode

```c
HRESULT __stdcall DwmSetIconicThumbnail(HWND hwnd, HBITMAP hbmp, DWORD dwSITFlags)
{
  bool v6; // bl
  HWND ShellWindow; // rax
  int ObjectW; // eax
  bool v9; // cl
  LONG v10; // ebx
  int v11; // r14d
  LONG v12; // esi
  unsigned int v13; // ebx
  __int64 v14; // rcx
  unsigned __int16 v15; // ax
  __int64 v16; // rcx
  signed int v17; // eax
  int v18; // r14d
  int v19; // eax
  int v20; // r9d
  unsigned int v22; // [rsp+20h] [rbp-A9h]
  void *v23; // [rsp+28h] [rbp-A1h]
  DWORD dwProcessId[2]; // [rsp+30h] [rbp-99h] BYREF
  tagSIZE v25; // [rsp+38h] [rbp-91h] BYREF
  void **v26; // [rsp+40h] [rbp-89h] BYREF
  __int128 v27; // [rsp+48h] [rbp-81h]
  int v28; // [rsp+58h] [rbp-71h] BYREF
  HWND v29; // [rsp+5Ch] [rbp-6Dh]
  LONG v30; // [rsp+64h] [rbp-65h]
  LONG v31; // [rsp+68h] [rbp-61h]
  DWORD v32; // [rsp+6Ch] [rbp-5Dh]
  _BYTE pv[4]; // [rsp+70h] [rbp-59h] BYREF
  int v34; // [rsp+74h] [rbp-55h]
  int v35; // [rsp+78h] [rbp-51h]
  unsigned __int16 v36; // [rsp+82h] [rbp-47h]
  int v37; // [rsp+B0h] [rbp-19h]

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(hwnd, ApiSetIconicThumbnail_Start, hwnd);
  v26 = &CStandardData::`vftable';
  v6 = 0;
  v27 = 0;
  ShellWindow = GetShellWindow();
  if ( ShellWindow )
  {
    dwProcessId[0] = 0;
    GetWindowThreadProcessId(ShellWindow, dwProcessId);
    v6 = GetCurrentProcessId() == dwProcessId[0];
  }
  if ( !hwnd || !hbmp || !v6 && !IsHwndInProcess(hwnd) )
  {
    v22 = 653;
    goto LABEL_35;
  }
  memset_0(pv, 0, 0x68u);
  ObjectW = GetObjectW(hbmp, 104, pv);
  v10 = -v34;
  *(_QWORD *)dwProcessId = 0;
  v11 = ObjectW;
  if ( v34 > 0 )
    v10 = v34;
  v12 = -v35;
  v25 = 0;
  if ( v35 > 0 )
    v12 = v35;
  dwProcessId[1] = v12;
  dwProcessId[0] = v10;
  if ( !(unsigned int)DwmGetIdealIconicThumbnailSize(v9, &v25) )
  {
    v13 = -2147467259;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A178, 2u, -2147467259, 0x298u, v23);
    goto LABEL_37;
  }
  if ( v11 != 104 || (v15 = v36, v36 != 32) || v37 )
  {
    v22 = 671;
    goto LABEL_35;
  }
  if ( v10 > v25.cx || v12 > v25.cy )
  {
    if ( !GetWindowTabOwner(hwnd) )
    {
      v22 = 678;
LABEL_35:
      v20 = -2147024809;
      v13 = -2147024809;
      goto LABEL_36;
    }
    v15 = v36;
  }
  v16 = 8;
  v17 = v12 * v10 * v15 / 8;
  v18 = v17;
  if ( v17 <= 0 )
    goto LABEL_29;
  v19 = CApiPortClient::LockExtraDataPointer((CApiPortClient *)8, v17, (struct CStandardData *)&v26);
  v13 = v19;
  if ( v19 < 0 )
  {
    v22 = 684;
    goto LABEL_27;
  }
  v19 = CopyBitmapHelper(hbmp, (struct tagSIZE *)dwProcessId, v18, *(char **)(*((_QWORD *)&v27 + 1) + 24LL));
  v13 = v19;
  if ( v19 >= 0 )
  {
    v12 = dwProcessId[1];
    v10 = dwProcessId[0];
LABEL_29:
    v28 = 1073741882;
    dwProcessId[0] = 0;
    v32 = dwSITFlags;
    v29 = hwnd;
    v30 = v10;
    v31 = v12;
    v19 = CApiPortClient::SendRequestValidate(
            (CApiPortClient *)v16,
            &v28,
            0x18u,
            (const struct CExtraData *)&v26,
            (int *)dwProcessId);
    v13 = v19;
    if ( v19 >= 0 )
    {
      v13 = dwProcessId[0];
      goto LABEL_37;
    }
    v22 = 698;
    goto LABEL_27;
  }
  v22 = 686;
LABEL_27:
  v20 = v19;
LABEL_36:
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A178, 2u, v20, v22, v23);
LABEL_37:
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0qp_EtwEventWriteTransfer(v14, ApiSetIconicThumbnail_Stop, v13, hwnd);
  CStandardData::~CStandardData((CStandardData *)&v26);
  return v13;
}

```

## disassembly

```asm
0x180013ed0  push    rbp
0x180013ed2  push    rbx
0x180013ed3  push    rsi
0x180013ed4  push    rdi
0x180013ed5  push    r12
0x180013ed7  push    r14
0x180013ed9  push    r15
0x180013edb  lea     rbp, [rsp-27h]
0x180013ee0  sub     rsp, 0F0h
0x180013ee7  mov     rax, cs:__security_cookie
0x180013eee  xor     rax, rsp
0x180013ef1  mov     [rbp+57h+var_40], rax
0x180013ef5  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180013efc  mov     r12d, r8d
0x180013eff  mov     r15, rdx
0x180013f02  mov     rdi, rcx
0x180013f05  jz      short loc_180013F16
0x180013f07  mov     r8, rcx
0x180013f0a  lea     rdx, ApiSetIconicThumbnail_Start
0x180013f11  call    McTemplateU0p_EtwEventWriteTransfer
0x180013f16  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180013f1d  xorps   xmm0, xmm0
0x180013f20  mov     [rsp+120h+var_E0], rax
0x180013f25  xor     bl, bl
0x180013f27  movdqu  [rsp+120h+var_D8], xmm0
0x180013f2d  call    cs:__imp_GetShellWindow
0x180013f33  test    rax, rax
0x180013f36  jz      short loc_180013F5B
0x180013f38  lea     rdx, [rsp+120h+dwProcessId]; lpdwProcessId
0x180013f3d  mov     [rsp+120h+dwProcessId], 0
0x180013f45  mov     rcx, rax; hWnd
0x180013f48  call    cs:__imp_GetWindowThreadProcessId
0x180013f4e  call    cs:__imp_GetCurrentProcessId
0x180013f54  cmp     eax, [rsp+120h+dwProcessId]
0x180013f58  setz    bl
0x180013f5b  test    rdi, rdi
0x180013f5e  jz      loc_18001410F
0x180013f64  test    r15, r15
0x180013f67  jz      loc_18001410F
0x180013f6d  test    bl, bl
0x180013f6f  jnz     short loc_180013F81
0x180013f71  mov     rcx, rdi; hWnd
0x180013f74  call    ?IsHwndInProcess@@YA_NPEAUHWND__@@@Z; IsHwndInProcess(HWND__ *)
0x180013f79  test    al, al
0x180013f7b  jz      loc_18001410F
0x180013f81  mov     ebx, 68h ; 'h'
0x180013f86  lea     rcx, [rbp+57h+pv]; void *
0x180013f8a  mov     r8d, ebx; Size
0x180013f8d  xor     edx, edx; Val
0x180013f8f  call    memset_0
0x180013f94  lea     r8, [rbp+57h+pv]; pv
0x180013f98  mov     edx, ebx; c
0x180013f9a  mov     rcx, r15; h
0x180013f9d  call    cs:__imp_GetObjectW
0x180013fa3  mov     ebx, [rbp+57h+var_AC]
0x180013fa6  lea     rdx, [rsp+120h+var_E8]; struct tagSIZE *
0x180013fab  mov     esi, [rbp+57h+var_A8]
0x180013fae  neg     ebx
0x180013fb0  mov     qword ptr [rsp+120h+dwProcessId], 0
0x180013fb9  mov     r14d, eax
0x180013fbc  cmovs   ebx, [rbp+57h+var_AC]
0x180013fc0  neg     esi
0x180013fc2  mov     qword ptr [rsp+120h+var_E8.cx], 0
0x180013fcb  cmovs   esi, [rbp+57h+var_A8]
0x180013fcf  mov     [rsp+120h+dwProcessId+4], esi
0x180013fd3  mov     [rsp+120h+dwProcessId], ebx
0x180013fd7  call    ?DwmGetIdealIconicThumbnailSize@@YAH_NPEAUtagSIZE@@@Z; DwmGetIdealIconicThumbnailSize(bool,tagSIZE *)
0x180013fdc  test    eax, eax
0x180013fde  jnz     short loc_180013FF5
0x180013fe0  mov     ebx, 80004005h
0x180013fe5  mov     dword ptr [rsp+120h+var_100], 298h
0x180013fed  mov     r9d, ebx
0x180013ff0  jmp     loc_180014120
0x180013ff5  cmp     r14d, 68h ; 'h'
0x180013ff9  jnz     loc_180014105
0x180013fff  movzx   eax, [rbp+57h+var_9E]
0x180014003  cmp     ax, 20h ; ' '
0x180014007  jnz     loc_180014105
0x18001400d  cmp     [rbp+57h+var_70], 0
0x180014011  ja      loc_180014105
0x180014017  cmp     ebx, [rsp+120h+var_E8.cx]
0x18001401b  jg      short loc_180014023
0x18001401d  cmp     esi, [rsp+120h+var_E8.cy]
0x180014021  jle     short loc_180014041
0x180014023  mov     rcx, rdi; HWND
0x180014026  call    ?GetWindowTabOwner@@YAPEAUHWND__@@QEAU1@@Z; GetWindowTabOwner(HWND__ * const)
0x18001402b  test    rax, rax
0x18001402e  jnz     short loc_18001403D
0x180014030  mov     dword ptr [rsp+120h+var_100], 2A6h
0x180014038  jmp     loc_180014117
0x18001403d  movzx   eax, [rbp+57h+var_9E]
0x180014041  movzx   eax, ax
0x180014044  mov     ecx, 8; this
0x180014049  imul    eax, ebx
0x18001404c  imul    eax, esi
0x18001404f  cdq
0x180014050  idiv    ecx
0x180014052  mov     r14d, eax
0x180014055  test    eax, eax
0x180014057  jle     short loc_1800140A5
0x180014059  lea     r8, [rsp+120h+var_E0]; struct CStandardData *
0x18001405e  mov     edx, eax; unsigned int
0x180014060  call    ?LockExtraDataPointer@CApiPortClient@@QEAAJIPEAVCStandardData@@@Z; CApiPortClient::LockExtraDataPointer(uint,CStandardData *)
0x180014065  mov     ebx, eax
0x180014067  test    eax, eax
0x180014069  js      loc_1800140F1
0x18001406f  mov     r9, qword ptr [rbp+57h+var_D8+8]
0x180014073  lea     rdx, [rsp+120h+dwProcessId]; struct tagSIZE *
0x180014078  mov     r8d, r14d; int
0x18001407b  mov     rcx, r15; hbm
0x18001407e  mov     r9, [r9+18h]; void *
0x180014082  call    ?CopyBitmapHelper@@YAJPEAUHBITMAP__@@PEAUtagSIZE@@HPEAX@Z; CopyBitmapHelper(HBITMAP__ *,tagSIZE *,int,void *)
0x180014087  mov     ebx, eax
0x180014089  test    eax, eax
0x18001408b  jns     short loc_18001409D
0x18001408d  mov     dword ptr [rsp+120h+var_100], 2AEh
0x180014095  mov     r9d, eax
0x180014098  jmp     loc_180014120
0x18001409d  mov     esi, [rsp+120h+dwProcessId+4]
0x1800140a1  mov     ebx, [rsp+120h+dwProcessId]
0x1800140a5  xor     eax, eax
0x1800140a7  mov     [rbp+57h+var_C8], 4000003Ah
0x1800140ae  mov     [rsp+120h+dwProcessId], eax
0x1800140b2  lea     r9, [rsp+120h+var_E0]; struct CExtraData *
0x1800140b7  xorps   xmm0, xmm0
0x1800140ba  mov     [rbp+57h+var_B4], r12d
0x1800140be  movups  [rbp+57h+var_C4], xmm0
0x1800140c2  lea     rax, [rsp+120h+dwProcessId]
0x1800140c7  mov     qword ptr [rbp+57h+var_C4], rdi
0x1800140cb  mov     r8d, 18h; unsigned __int64
0x1800140d1  mov     [rsp+120h+var_100], rax; int *
0x1800140d6  lea     rdx, [rbp+57h+var_C8]; void *
0x1800140da  mov     dword ptr [rbp+57h+var_C4+8], ebx
0x1800140dd  mov     dword ptr [rbp+57h+var_C4+0Ch], esi
0x1800140e0  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KAEBVCExtraData@@PEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,CExtraData const &,long *)
0x1800140e5  mov     ebx, eax
0x1800140e7  test    eax, eax
0x1800140e9  js      short loc_1800140FB
0x1800140eb  mov     ebx, [rsp+120h+dwProcessId]
0x1800140ef  jmp     short loc_180014136
0x1800140f1  mov     dword ptr [rsp+120h+var_100], 2ACh
0x1800140f9  jmp     short loc_180014095
0x1800140fb  mov     dword ptr [rsp+120h+var_100], 2BAh
0x180014103  jmp     short loc_180014095
0x180014105  mov     dword ptr [rsp+120h+var_100], 29Fh
0x18001410d  jmp     short loc_180014117
0x18001410f  mov     dword ptr [rsp+120h+var_100], 28Dh; unsigned int
0x180014117  mov     r9d, 80070057h; int
0x18001411d  mov     ebx, r9d
0x180014120  mov     r8d, 2; unsigned int
0x180014126  lea     rdx, qword_18001A178; int *
0x18001412d  lea     ecx, [r8+2]; unsigned int
0x180014131  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180014136  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18001413d  jz      short loc_180014151
0x18001413f  mov     r9, rdi
0x180014142  lea     rdx, ApiSetIconicThumbnail_Stop
0x180014149  mov     r8d, ebx
0x18001414c  call    McTemplateU0qp_EtwEventWriteTransfer
0x180014151  lea     rcx, [rsp+120h+var_E0]; this
0x180014156  call    ??1CStandardData@@UEAA@XZ; CStandardData::~CStandardData(void)
0x18001415b  mov     eax, ebx
0x18001415d  mov     rcx, [rbp+57h+var_40]
0x180014161  xor     rcx, rsp; StackCookie
0x180014164  call    __security_check_cookie
0x180014169  add     rsp, 0F0h
0x180014170  pop     r15
0x180014172  pop     r14
0x180014174  pop     r12
0x180014176  pop     rdi
0x180014177  pop     rsi
0x180014178  pop     rbx
0x180014179  pop     rbp
0x18001417a  retn
```
