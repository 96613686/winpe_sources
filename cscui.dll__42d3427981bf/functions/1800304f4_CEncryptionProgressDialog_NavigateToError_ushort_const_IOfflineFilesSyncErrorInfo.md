# CEncryptionProgressDialog::_NavigateToError(ushort const *,IOfflineFilesSyncErrorInfo *)

- ea: `0x1800304f4`
- end: `0x18003066e`
- name: `?_NavigateToError@CEncryptionProgressDialog@@AEAAJPEBGPEAUIOfflineFilesSyncErrorInfo@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(CEncryptionProgressDialog *__hidden this, const unsigned __int16 *, struct IOfflineFilesSyncErrorInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030918`

## callees

- `0x180003a90`
- `0x180003c20`
- `0x180010ff4`
- `0x18001101c`
- `0x180013d9c`
- `0x1800304f4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030627`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030627`
- `USER32!SendMessageW` at `0x1800305f0`
- `USER32!SendMessageW` at `0x1800305f0`

## pseudocode

```c
__int64 __fastcall CEncryptionProgressDialog::_NavigateToError(
        CEncryptionProgressDialog *this,
        unsigned __int16 *a2,
        struct IOfflineFilesSyncErrorInfo *a3)
{
  struct IOfflineFilesSyncErrorInfoVtbl *lpVtbl; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids);
  }
  CscUtil_HeapFree(*((void **)this + 56), a2);
  *((_QWORD *)this + 56) = 0;
  lpVtbl = a3->lpVtbl;
  pv = 0;
  v7 = ((__int64 (__fastcall *)(struct IOfflineFilesSyncErrorInfo *, LPVOID *))lpVtbl->GetDescription)(a3, &pv);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids,
        (unsigned int)v7);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids, pv);
    }
    v9 = CscUtil_FormatStringID(
           (LPWSTR)this + 224,
           g_hInstance,
           4414 - (unsigned int)(*((_DWORD *)this + 12) != 0),
           a2,
           pv);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids,
          (unsigned int)v9);
      }
    }
    else
    {
      SendMessageW(*((HWND *)this + 4), 0x465u, 0, (LPARAM)this + 220);
    }
    CoTaskMemFree(pv);
  }
  return v8;
}

```

## disassembly

```asm
0x1800304f4  mov     [rsp+arg_8], rbx
0x1800304f9  mov     [rsp+arg_10], rbp
0x1800304fe  push    rsi
0x1800304ff  push    rdi
0x180030500  push    r14
0x180030502  sub     rsp, 30h
0x180030506  mov     rbx, r8
0x180030509  mov     rbp, rdx
0x18003050c  mov     rdi, rcx
0x18003050f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030516  lea     r14, WPP_GLOBAL_Control
0x18003051d  cmp     rcx, r14
0x180030520  jz      short loc_180030540
0x180030522  test    dword ptr [rcx+1Ch], 1000000h
0x180030529  jz      short loc_180030540
0x18003052b  mov     rcx, [rcx+10h]
0x18003052f  lea     r8, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids
0x180030536  mov     edx, 32h ; '2'
0x18003053b  call    WPP_SF_
0x180030540  lea     rsi, [rdi+1C0h]
0x180030547  mov     rcx, [rsi]; lpMem
0x18003054a  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18003054f  mov     qword ptr [rsi], 0
0x180030556  lea     rdx, [rsp+48h+pv]
0x18003055b  mov     rax, [rbx]
0x18003055e  mov     rcx, rbx
0x180030561  mov     [rsp+48h+pv], 0
0x18003056a  mov     rax, [rax+20h]
0x18003056e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030573  mov     ebx, eax
0x180030575  test    eax, eax
0x180030577  js      loc_18003062F
0x18003057d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030584  cmp     rcx, r14
0x180030587  jz      short loc_1800305AC
0x180030589  test    dword ptr [rcx+1Ch], 1000000h
0x180030590  jz      short loc_1800305AC
0x180030592  mov     r9, [rsp+48h+pv]
0x180030597  lea     r8, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids
0x18003059e  mov     rcx, [rcx+10h]
0x1800305a2  mov     edx, 33h ; '3'
0x1800305a7  call    WPP_SF_S
0x1800305ac  mov     eax, [rdi+30h]
0x1800305af  mov     r9, rbp
0x1800305b2  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800305b9  neg     eax
0x1800305bb  mov     rax, [rsp+48h+pv]
0x1800305c0  mov     rcx, rsi; lpBuffer
0x1800305c3  sbb     r8d, r8d
0x1800305c6  mov     [rsp+48h+var_28], rax
0x1800305cb  add     r8d, 113Eh; uID
0x1800305d2  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x1800305d7  mov     ebx, eax
0x1800305d9  test    eax, eax
0x1800305db  js      short loc_1800305F8
0x1800305dd  mov     rcx, [rdi+20h]; hWnd
0x1800305e1  lea     r9, [rdi+0DCh]; lParam
0x1800305e8  xor     r8d, r8d; wParam
0x1800305eb  mov     edx, 465h; Msg
0x1800305f0  call    cs:__imp_SendMessageW
0x1800305f6  jmp     short loc_180030622
0x1800305f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305ff  cmp     rcx, r14
0x180030602  jz      short loc_180030622
0x180030604  test    byte ptr [rcx+1Ch], 2
0x180030608  jz      short loc_180030622
0x18003060a  mov     rcx, [rcx+10h]
0x18003060e  lea     r8, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids
0x180030615  mov     edx, 34h ; '4'
0x18003061a  mov     r9d, eax
0x18003061d  call    WPP_SF_d
0x180030622  mov     rcx, [rsp+48h+pv]; pv
0x180030627  call    cs:__imp_CoTaskMemFree
0x18003062d  jmp     short loc_180030659
0x18003062f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030636  cmp     rcx, r14
0x180030639  jz      short loc_180030659
0x18003063b  test    byte ptr [rcx+1Ch], 2
0x18003063f  jz      short loc_180030659
0x180030641  mov     rcx, [rcx+10h]
0x180030645  lea     r8, WPP_36c076e4197e3fd7375ce9da5d010b72_Traceguids
0x18003064c  mov     edx, 35h ; '5'
0x180030651  mov     r9d, eax
0x180030654  call    WPP_SF_d
0x180030659  mov     rbp, [rsp+48h+arg_10]
0x18003065e  mov     eax, ebx
0x180030660  mov     rbx, [rsp+48h+arg_8]
0x180030665  add     rsp, 30h
0x180030669  pop     r14
0x18003066b  pop     rdi
0x18003066c  pop     rsi
0x18003066d  retn
```
