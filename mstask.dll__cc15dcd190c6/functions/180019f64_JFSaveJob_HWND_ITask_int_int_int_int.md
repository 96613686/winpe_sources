# JFSaveJob(HWND__ *,ITask *,int,int,int,int)

- ea: `0x180019f64`
- end: `0x18001a1cc`
- name: `?JFSaveJob@@YAJPEAUHWND__@@PEAUITask@@HHHH@Z`
- size: `616`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct ITask *@<rdx>, int@<r8d>, int@<r9d>, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800116c0`
- `0x180014620`
- `0x180017130`

## callees

- `0x18001068c`
- `0x180019f30`
- `0x180019f64`
- `0x18001a1d4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a097`
- `USER32!DialogBoxParamW` at `0x18001a101`
- `USER32!DialogBoxParamW` at `0x18001a101`
- `USER32!SetCursor` at `0x18001a18d`
- `USER32!SetCursor` at `0x18001a18d`

## pseudocode

```c
__int64 __fastcall JFSaveJob(HWND a1, struct ITask *a2, int a3, int a4, int a5, int a6)
{
  struct ITaskVtbl *lpVtbl; // rax
  int v10; // r14d
  HRESULT (__stdcall *QueryInterface)(ITask *, const IID *const, void **); // rax
  __int64 result; // rax
  int v14; // ebx
  int v15; // esi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  HCURSOR hCursor; // [rsp+38h] [rbp-30h] BYREF
  LPARAM dwInitParam[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-18h]
  LPVOID pv; // [rsp+B8h] [rbp+50h] BYREF

  v22 = 0;
  lpVtbl = a2->lpVtbl;
  v10 = 0;
  v19 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  *(_OWORD *)dwInitParam = 0;
  pv = 0;
  result = ((__int64 (__fastcall *)(struct ITask *, GUID *, __int64 *))QueryInterface)(a2, &IID_IPersistFile, &v19);
  v14 = result;
  if ( (int)result < 0 )
    return result;
  v15 = a5;
  if ( a3 )
  {
    dwInitParam[0] = 0;
    dwInitParam[1] = (LPARAM)&String;
    if ( a5 )
    {
      if ( !a4 )
      {
        if ( ((int (__fastcall *)(struct ITask *, LPVOID *))a2->lpVtbl->GetAccountInformation)(a2, &pv) < 0 )
          goto LABEL_22;
        goto LABEL_21;
      }
    }
  }
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL))(v19, 0, 0);
  v14 = v16;
  if ( a3 )
  {
    if ( v16 >= 0 )
    {
      v10 = 1;
      if ( a4 )
      {
        if ( v15 )
        {
          v18 = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a2->lpVtbl->GetAccountInformation)(a2, &pv);
          v14 = v18;
          if ( v18 >= 0 && v18 != 1 )
          {
LABEL_21:
            dwInitParam[0] = (LPARAM)pv;
LABEL_22:
            if ( a6
              || (DialogBoxParamW(
                    g_hInstance,
                    (LPCWSTR)0x67,
                    a1,
                    (DLGPROC)SetAccountInformationDlgProc,
                    (LPARAM)dwInitParam),
                  !dwInitParam[0])
              || (const WCHAR *)dwInitParam[1] == &String
              || (v14 = ((__int64 (__fastcall *)(struct ITask *))a2->lpVtbl->SetAccountInformation)(a2),
                  v10 = 0,
                  v14 >= 0) )
            {
              if ( !v10 )
              {
                CWaitCursor::CWaitCursor((CWaitCursor *)&hCursor);
                v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v19 + 48LL))(v19, 0, 0);
                if ( v14 < 0 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19) == 1 )
                {
                  SecurityErrorDialog(a1, v14);
                  v14 = 0;
                }
                SetCursor(hCursor);
              }
            }
            goto LABEL_32;
          }
          goto LABEL_31;
        }
      }
      else
      {
        v17 = ((__int64 (__fastcall *)(struct ITask *, LPVOID *))a2->lpVtbl->GetAccountInformation)(a2, &pv);
        v14 = v17;
        if ( v17 == -2147216625 )
        {
          v14 = 0;
          goto LABEL_22;
        }
        if ( v17 < 0 )
          goto LABEL_31;
        if ( *(_WORD *)pv )
        {
          dwInitParam[0] = (LPARAM)pv;
          goto LABEL_22;
        }
        CoTaskMemFree(pv);
      }
    }
    else if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19) == 1 )
    {
      SecurityErrorDialog(a1, v14);
LABEL_31:
      v14 = 0;
    }
  }
LABEL_32:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( a3 )
    ResetAccountInfo((struct _AccountInfo *)dwInitParam);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180019f64  push    rbp
0x180019f66  push    rbx
0x180019f67  push    rsi
0x180019f68  push    rdi
0x180019f69  push    r12
0x180019f6b  push    r13
0x180019f6d  push    r14
0x180019f6f  push    r15
0x180019f71  mov     rbp, rsp
0x180019f74  sub     rsp, 68h
0x180019f78  xor     eax, eax
0x180019f7a  mov     rdi, rdx
0x180019f7d  mov     [rbp+var_18], rax
0x180019f81  mov     r13d, r8d
0x180019f84  mov     rax, [rdx]
0x180019f87  lea     r8, [rbp+var_38]
0x180019f8b  mov     r12, rcx
0x180019f8e  lea     rdx, IID_IPersistFile
0x180019f95  xorps   xmm0, xmm0
0x180019f98  xor     r14d, r14d
0x180019f9b  mov     rcx, rdi
0x180019f9e  mov     [rbp+var_38], r14
0x180019fa2  mov     rax, [rax]
0x180019fa5  mov     r15d, r9d
0x180019fa8  movups  xmmword ptr [rbp+var_28], xmm0
0x180019fac  mov     [rbp+pv], r14
0x180019fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb5  mov     ebx, eax
0x180019fb7  test    eax, eax
0x180019fb9  js      loc_18001A1BB
0x180019fbf  mov     esi, [rbp+arg_20]
0x180019fc2  lea     rax, String
0x180019fc9  test    r13d, r13d
0x180019fcc  jz      short loc_18001A004
0x180019fce  mov     [rbp+var_28], r14
0x180019fd2  mov     [rbp+var_28+8], rax
0x180019fd6  test    esi, esi
0x180019fd8  jz      short loc_18001A004
0x180019fda  test    r15d, r15d
0x180019fdd  jnz     short loc_18001A004
0x180019fdf  mov     rax, [rdi]
0x180019fe2  lea     rdx, [rbp+pv]
0x180019fe6  mov     rcx, rdi
0x180019fe9  mov     rax, [rax+0F8h]
0x180019ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff5  xor     esi, esi
0x180019ff7  test    eax, eax
0x180019ff9  js      loc_18001A0DD
0x180019fff  jmp     loc_18001A0D5
0x18001a004  mov     rcx, [rbp+var_38]
0x18001a008  xor     r8d, r8d
0x18001a00b  xor     edx, edx
0x18001a00d  mov     rax, [rcx]
0x18001a010  mov     rax, [rax+30h]
0x18001a014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a019  mov     ebx, eax
0x18001a01b  test    r13d, r13d
0x18001a01e  jz      loc_18001A19B
0x18001a024  test    eax, eax
0x18001a026  jns     short loc_18001A050
0x18001a028  mov     rcx, [rbp+var_38]
0x18001a02c  mov     rax, [rcx]
0x18001a02f  mov     rax, [rax+20h]
0x18001a033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a038  cmp     eax, 1
0x18001a03b  jnz     loc_18001A19B
0x18001a041  mov     edx, ebx; int
0x18001a043  mov     rcx, r12; HWND
0x18001a046  call    ?SecurityErrorDialog@@YAXPEAUHWND__@@J@Z; SecurityErrorDialog(HWND__ *,long)
0x18001a04b  jmp     loc_18001A198
0x18001a050  mov     r14d, 1
0x18001a056  test    r15d, r15d
0x18001a059  jnz     short loc_18001A0A2
0x18001a05b  mov     rax, [rdi]
0x18001a05e  lea     rdx, [rbp+pv]
0x18001a062  mov     rcx, rdi
0x18001a065  mov     rax, [rax+0F8h]
0x18001a06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a071  xor     esi, esi
0x18001a073  mov     ebx, eax
0x18001a075  cmp     eax, 8004130Fh
0x18001a07a  jnz     short loc_18001A080
0x18001a07c  mov     ebx, esi
0x18001a07e  jmp     short loc_18001A0DD
0x18001a080  test    eax, eax
0x18001a082  js      loc_18001A195
0x18001a088  mov     rcx, [rbp+pv]; pv
0x18001a08c  cmp     [rcx], si
0x18001a08f  jz      short loc_18001A097
0x18001a091  mov     [rbp+var_28], rcx
0x18001a095  jmp     short loc_18001A0DD
0x18001a097  call    cs:__imp_CoTaskMemFree
0x18001a09d  jmp     loc_18001A19B
0x18001a0a2  test    esi, esi
0x18001a0a4  jz      loc_18001A19B
0x18001a0aa  mov     rax, [rdi]
0x18001a0ad  lea     rdx, [rbp+pv]
0x18001a0b1  mov     rcx, rdi
0x18001a0b4  mov     rax, [rax+0F8h]
0x18001a0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0c0  mov     ebx, eax
0x18001a0c2  test    eax, eax
0x18001a0c4  js      loc_18001A195
0x18001a0ca  cmp     eax, r14d
0x18001a0cd  jz      loc_18001A195
0x18001a0d3  xor     esi, esi
0x18001a0d5  mov     rax, [rbp+pv]
0x18001a0d9  mov     [rbp+var_28], rax
0x18001a0dd  cmp     [rbp+arg_28], esi
0x18001a0e0  jnz     short loc_18001A13B
0x18001a0e2  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001a0e9  lea     rax, [rbp+var_28]
0x18001a0ed  lea     r9, ?SetAccountInformationDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001a0f4  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x18001a0f9  mov     r8, r12; hWndParent
0x18001a0fc  mov     edx, 67h ; 'g'; lpTemplateName
0x18001a101  call    cs:__imp_DialogBoxParamW
0x18001a107  mov     rdx, [rbp+var_28]
0x18001a10b  test    rdx, rdx
0x18001a10e  jz      short loc_18001A13B
0x18001a110  mov     r8, [rbp+var_28+8]
0x18001a114  lea     rax, String
0x18001a11b  cmp     r8, rax
0x18001a11e  jz      short loc_18001A13B
0x18001a120  mov     rax, [rdi]
0x18001a123  mov     rcx, rdi
0x18001a126  mov     rax, [rax+0F0h]
0x18001a12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a132  mov     ebx, eax
0x18001a134  mov     r14d, esi
0x18001a137  test    eax, eax
0x18001a139  js      short loc_18001A19B
0x18001a13b  test    r14d, r14d
0x18001a13e  jnz     short loc_18001A19B
0x18001a140  lea     rcx, [rbp+hCursor]; this
0x18001a144  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18001a149  mov     rcx, [rbp+var_38]
0x18001a14d  xor     r8d, r8d
0x18001a150  xor     edx, edx
0x18001a152  mov     rax, [rcx]
0x18001a155  mov     rax, [rax+30h]
0x18001a159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a15e  xor     r14d, r14d
0x18001a161  mov     ebx, eax
0x18001a163  test    eax, eax
0x18001a165  jns     short loc_18001A189
0x18001a167  mov     rcx, [rbp+var_38]
0x18001a16b  mov     rax, [rcx]
0x18001a16e  mov     rax, [rax+20h]
0x18001a172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a177  cmp     eax, 1
0x18001a17a  jnz     short loc_18001A189
0x18001a17c  mov     edx, ebx; int
0x18001a17e  mov     rcx, r12; HWND
0x18001a181  call    ?SecurityErrorDialog@@YAXPEAUHWND__@@J@Z; SecurityErrorDialog(HWND__ *,long)
0x18001a186  mov     ebx, r14d
0x18001a189  mov     rcx, [rbp+hCursor]; hCursor
0x18001a18d  call    cs:__imp_SetCursor
0x18001a193  jmp     short loc_18001A19B
0x18001a195  xor     r14d, r14d
0x18001a198  mov     ebx, r14d
0x18001a19b  mov     rcx, [rbp+var_38]
0x18001a19f  mov     rax, [rcx]
0x18001a1a2  mov     rax, [rax+10h]
0x18001a1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ab  test    r13d, r13d
0x18001a1ae  jz      short loc_18001A1B9
0x18001a1b0  lea     rcx, [rbp+var_28]; struct _AccountInfo *
0x18001a1b4  call    ?ResetAccountInfo@@YAXPEAU_AccountInfo@@@Z; ResetAccountInfo(_AccountInfo *)
0x18001a1b9  mov     eax, ebx
0x18001a1bb  add     rsp, 68h
0x18001a1bf  pop     r15
0x18001a1c1  pop     r14
0x18001a1c3  pop     r13
0x18001a1c5  pop     r12
0x18001a1c7  pop     rdi
0x18001a1c8  pop     rsi
0x18001a1c9  pop     rbx
0x18001a1ca  pop     rbp
0x18001a1cb  retn
```
