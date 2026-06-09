# DeletePermanentPipeline

- ea: `0x1800240b4`
- end: `0x1800243a5`
- name: `DeletePermanentPipeline`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024750`

## callees

- `0x1800240b4`
- `0x18004484e`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x18002411c`
- `mi!MI_Application_InitializeV1` at `0x18002411c`

## pseudocode

```c
const MI_ApplicationFT *DeletePermanentPipeline()
{
  const MI_ApplicationFT *result; // rax
  int v1; // eax
  __int64 v2; // rax
  int v3; // [rsp+28h] [rbp-81h]
  char v4; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v5[3]; // [rsp+51h] [rbp-58h] BYREF
  MI_Result v6; // [rsp+54h] [rbp-55h] BYREF
  int v7; // [rsp+58h] [rbp-51h] BYREF
  int v8; // [rsp+5Ch] [rbp-4Dh] BYREF
  __int64 v9; // [rsp+60h] [rbp-49h] BYREF
  __int128 v10; // [rsp+68h] [rbp-41h] BYREF
  __int64 v11; // [rsp+78h] [rbp-31h]
  __int128 v12; // [rsp+80h] [rbp-29h] BYREF
  __int64 v13; // [rsp+90h] [rbp-19h]
  __int128 v14; // [rsp+98h] [rbp-11h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-1h]
  MI_Application application; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v17; // [rsp+C8h] [rbp+1Fh] BYREF
  wchar_t *String1[2]; // [rsp+D0h] [rbp+27h] BYREF
  __int128 v19; // [rsp+E0h] [rbp+37h]
  __int64 v20; // [rsp+F0h] [rbp+47h]

  v4 = 1;
  v11 = 0;
  v13 = 0;
  result = (const MI_ApplicationFT *)g_permanentPipelinesSkipPipelineExecutionDeletion;
  v6 = MI_RESULT_OK;
  v9 = 0;
  memset(&application, 0, sizeof(application));
  v10 = 0;
  v12 = 0;
  if ( !g_permanentPipelinesSkipPipelineExecutionDeletion )
  {
    v6 = MI_Application_InitializeV1(0, 0, 0, &application);
    if ( v6 == MI_RESULT_OK )
    {
      if ( application.ft )
      {
        v6 = ((unsigned int (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, __int128 *))application.ft->NewSession)(
               &application,
               0,
               0,
               0,
               0,
               0,
               &v10);
        if ( v6 == MI_RESULT_OK )
        {
          if ( v11 )
          {
            LOBYTE(v3) = 0;
            (*(void (__fastcall **)(__int128 *, _QWORD, _QWORD, const wchar_t *, const wchar_t *, int, _QWORD, __int128 *))(v11 + 56))(
              &v10,
              0,
              0,
              L"root/PEH",
              L"MSFT_PipelineExecution",
              v3,
              0,
              &v12);
          }
          else
          {
            v12 = 0;
            v13 = 0;
          }
          while ( v4 )
          {
            v8 = 0;
            v20 = 0;
            *(_OWORD *)String1 = 0;
            v19 = 0;
            if ( v13 )
            {
              (*(void (__fastcall **)(__int128 *, __int64 *, char *, MI_Result *, _QWORD, _QWORD))(v13 + 24))(
                &v12,
                &v9,
                &v4,
                &v6,
                0,
                0);
              v1 = v6;
            }
            else
            {
              v1 = 4;
              v4 = 0;
              v6 = MI_RESULT_INVALID_PARAMETER;
            }
            if ( v1 )
              break;
            if ( !v9 || !*(_QWORD *)v9 )
              goto LABEL_27;
            v6 = (*(unsigned int (__fastcall **)(__int64, const wchar_t *, wchar_t **, int *, _QWORD, _QWORD))(*(_QWORD *)v9 + 88LL))(
                   v9,
                   L"Name",
                   String1,
                   &v8,
                   0,
                   0);
            if ( v6 )
              break;
            if ( String1[0] && !wcscmp_0(String1[0], L"DSC Local LCM") )
            {
              v2 = 0;
              v17 = 0;
              v15 = 0;
              v5[0] = 0;
              v7 = 0;
              v14 = 0;
              if ( v11 )
              {
                (*(void (__fastcall **)(__int128 *, _QWORD, _QWORD, const wchar_t *, __int64, _QWORD, __int128 *))(v11 + 40))(
                  &v10,
                  0,
                  0,
                  L"root/PEH",
                  v9,
                  0,
                  &v14);
                v2 = v15;
              }
              if ( v2 )
              {
                (*(void (__fastcall **)(__int128 *, __int64 *, _BYTE *, int *, _QWORD, _QWORD))(v2 + 24))(
                  &v14,
                  &v17,
                  v5,
                  &v7,
                  0,
                  0);
                v2 = v15;
              }
              else
              {
                v7 = 4;
                v5[0] = 0;
              }
              if ( v2 )
                (*(void (__fastcall **)(__int128 *))v2)(&v14);
            }
          }
        }
      }
      else
      {
        v10 = 0;
        v11 = 0;
LABEL_27:
        v6 = MI_RESULT_INVALID_PARAMETER;
      }
    }
    if ( v13 )
      (*(void (__fastcall **)(__int128 *))v13)(&v12);
    if ( v11 )
      (*(void (__fastcall **)(__int128 *, _QWORD, _QWORD))v11)(&v10, 0, 0);
    result = application.ft;
    if ( application.ft )
      return (const MI_ApplicationFT *)((__int64 (__fastcall *)(MI_Application *))application.ft->Close)(&application);
  }
  return result;
}

```

## disassembly

```asm
0x1800240b4  mov     [rsp-8+arg_0], rdi
0x1800240b9  push    rbp
0x1800240ba  lea     rbp, [rsp-57h]
0x1800240bf  sub     rsp, 100h
0x1800240c6  mov     rax, cs:__security_cookie
0x1800240cd  xor     rax, rsp
0x1800240d0  mov     [rbp+57h+var_8], rax
0x1800240d4  xor     eax, eax
0x1800240d6  mov     [rbp+57h+var_B0], 1
0x1800240da  xor     edi, edi
0x1800240dc  mov     [rbp+57h+application.ft], rax
0x1800240e0  xorps   xmm0, xmm0
0x1800240e3  mov     [rbp+57h+var_88], rax
0x1800240e7  mov     [rbp+57h+var_70], rax
0x1800240eb  xorps   xmm1, xmm1
0x1800240ee  mov     rax, cs:g_permanentPipelinesSkipPipelineExecutionDeletion
0x1800240f5  mov     [rbp+57h+var_AC], edi
0x1800240f8  mov     [rbp+57h+var_A0], rdi
0x1800240fc  movups  xmmword ptr [rbp+57h+application.reserved1], xmm0
0x180024100  movups  [rbp+57h+var_98], xmm1
0x180024104  movups  [rbp+57h+var_80], xmm0
0x180024108  test    rax, rax
0x18002410b  jnz     loc_180024388
0x180024111  lea     r9, [rbp+57h+application]; application
0x180024115  xor     r8d, r8d; extendedError
0x180024118  xor     edx, edx; applicationID
0x18002411a  xor     ecx, ecx; flags
0x18002411c  call    cs:__imp_MI_Application_InitializeV1
0x180024122  mov     [rbp+57h+var_AC], eax
0x180024125  test    eax, eax
0x180024127  jnz     loc_180024344
0x18002412d  mov     rax, [rbp+57h+application.ft]
0x180024131  test    rax, rax
0x180024134  jz      loc_180024330
0x18002413a  mov     rax, [rax+8]
0x18002413e  lea     rcx, [rbp+57h+var_98]
0x180024142  mov     [rsp+100h+var_D0], rcx
0x180024147  xor     r9d, r9d
0x18002414a  mov     [rsp+100h+var_D8], rdi
0x18002414f  lea     rcx, [rbp+57h+application]
0x180024153  xor     r8d, r8d
0x180024156  mov     [rsp+100h+var_E0], rdi
0x18002415b  xor     edx, edx
0x18002415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024162  mov     [rbp+57h+var_AC], eax
0x180024165  test    eax, eax
0x180024167  jnz     loc_180024344
0x18002416d  mov     rax, [rbp+57h+var_88]
0x180024171  test    rax, rax
0x180024174  jz      short loc_1800241B3
0x180024176  mov     rax, [rax+38h]
0x18002417a  lea     rcx, [rbp+57h+var_80]
0x18002417e  mov     [rsp+100h+var_C8], rcx
0x180024183  lea     r9, aRootPeh; "root/PEH"
0x18002418a  mov     [rsp+100h+var_D0], rdi
0x18002418f  lea     rcx, aMsftPipelineex; "MSFT_PipelineExecution"
0x180024196  mov     byte ptr [rsp+100h+var_D8], dil
0x18002419b  xor     r8d, r8d
0x18002419e  mov     [rsp+100h+var_E0], rcx
0x1800241a3  xor     edx, edx
0x1800241a5  lea     rcx, [rbp+57h+var_98]
0x1800241a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ae  jmp     loc_180024324
0x1800241b3  xorps   xmm0, xmm0
0x1800241b6  xor     eax, eax
0x1800241b8  movups  [rbp+57h+var_80], xmm0
0x1800241bc  mov     [rbp+57h+var_70], rax
0x1800241c0  jmp     loc_180024324
0x1800241c5  xor     eax, eax
0x1800241c7  mov     [rbp+57h+var_A4], edi
0x1800241ca  xorps   xmm0, xmm0
0x1800241cd  mov     [rbp+57h+var_10], rax
0x1800241d1  mov     rax, [rbp+57h+var_70]
0x1800241d5  movups  xmmword ptr [rbp+57h+String1], xmm0
0x1800241d9  movups  [rbp+57h+var_20], xmm0
0x1800241dd  test    rax, rax
0x1800241e0  jz      short loc_18002420A
0x1800241e2  mov     rax, [rax+18h]
0x1800241e6  lea     r9, [rbp+57h+var_AC]
0x1800241ea  mov     [rsp+100h+var_D8], rdi
0x1800241ef  lea     r8, [rbp+57h+var_B0]
0x1800241f3  lea     rdx, [rbp+57h+var_A0]
0x1800241f7  mov     [rsp+100h+var_E0], rdi
0x1800241fc  lea     rcx, [rbp+57h+var_80]
0x180024200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024205  mov     eax, [rbp+57h+var_AC]
0x180024208  jmp     short loc_180024216
0x18002420a  mov     eax, 4
0x18002420f  mov     [rbp+57h+var_B0], dil
0x180024213  mov     [rbp+57h+var_AC], eax
0x180024216  test    eax, eax
0x180024218  jnz     loc_180024344
0x18002421e  mov     rcx, [rbp+57h+var_A0]
0x180024222  test    rcx, rcx
0x180024225  jz      loc_18002433D
0x18002422b  mov     rax, [rcx]
0x18002422e  test    rax, rax
0x180024231  jz      loc_18002433D
0x180024237  mov     rax, [rax+58h]
0x18002423b  lea     r9, [rbp+57h+var_A4]
0x18002423f  mov     [rsp+100h+var_D8], rdi
0x180024244  lea     r8, [rbp+57h+String1]
0x180024248  lea     rdx, aName; "Name"
0x18002424f  mov     [rsp+100h+var_E0], rdi
0x180024254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024259  mov     [rbp+57h+var_AC], eax
0x18002425c  test    eax, eax
0x18002425e  jnz     loc_180024344
0x180024264  mov     rcx, [rbp+57h+String1]; String1
0x180024268  test    rcx, rcx
0x18002426b  jz      loc_180024324
0x180024271  lea     rdx, aDscLocalLcm; "DSC Local LCM"
0x180024278  call    wcscmp_0
0x18002427d  test    eax, eax
0x18002427f  jnz     loc_180024324
0x180024285  mov     r10, [rbp+57h+var_88]
0x180024289  xor     eax, eax
0x18002428b  mov     [rbp+57h+var_38], rdi
0x18002428f  xorps   xmm0, xmm0
0x180024292  mov     [rbp+57h+var_58], rax
0x180024296  mov     [rbp+57h+var_AF], dil
0x18002429a  mov     [rbp+57h+var_A8], edi
0x18002429d  movups  [rbp+57h+var_68], xmm0
0x1800242a1  test    r10, r10
0x1800242a4  jz      short loc_1800242DA
0x1800242a6  mov     rcx, [rbp+57h+var_A0]
0x1800242aa  lea     rax, [rbp+57h+var_68]
0x1800242ae  mov     [rsp+100h+var_D0], rax
0x1800242b3  lea     r9, aRootPeh; "root/PEH"
0x1800242ba  mov     rax, [r10+28h]
0x1800242be  xor     r8d, r8d
0x1800242c1  mov     [rsp+100h+var_D8], rdi
0x1800242c6  xor     edx, edx
0x1800242c8  mov     [rsp+100h+var_E0], rcx
0x1800242cd  lea     rcx, [rbp+57h+var_98]
0x1800242d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242d6  mov     rax, [rbp+57h+var_58]
0x1800242da  test    rax, rax
0x1800242dd  jz      short loc_180024308
0x1800242df  mov     rax, [rax+18h]
0x1800242e3  lea     r9, [rbp+57h+var_A8]
0x1800242e7  mov     [rsp+100h+var_D8], rdi
0x1800242ec  lea     r8, [rbp+57h+var_AF]
0x1800242f0  lea     rdx, [rbp+57h+var_38]
0x1800242f4  mov     [rsp+100h+var_E0], rdi
0x1800242f9  lea     rcx, [rbp+57h+var_68]
0x1800242fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024302  mov     rax, [rbp+57h+var_58]
0x180024306  jmp     short loc_180024313
0x180024308  mov     [rbp+57h+var_A8], 4
0x18002430f  mov     [rbp+57h+var_AF], dil
0x180024313  test    rax, rax
0x180024316  jz      short loc_180024324
0x180024318  mov     rax, [rax]
0x18002431b  lea     rcx, [rbp+57h+var_68]
0x18002431f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024324  cmp     [rbp+57h+var_B0], dil
0x180024328  jnz     loc_1800241C5
0x18002432e  jmp     short loc_180024344
0x180024330  xorps   xmm0, xmm0
0x180024333  xor     eax, eax
0x180024335  movups  [rbp+57h+var_98], xmm0
0x180024339  mov     [rbp+57h+var_88], rax
0x18002433d  mov     [rbp+57h+var_AC], 4
0x180024344  mov     rax, [rbp+57h+var_70]
0x180024348  test    rax, rax
0x18002434b  jz      short loc_180024359
0x18002434d  mov     rax, [rax]
0x180024350  lea     rcx, [rbp+57h+var_80]
0x180024354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024359  mov     rax, [rbp+57h+var_88]
0x18002435d  test    rax, rax
0x180024360  jz      short loc_180024373
0x180024362  mov     rax, [rax]
0x180024365  lea     rcx, [rbp+57h+var_98]
0x180024369  xor     r8d, r8d
0x18002436c  xor     edx, edx
0x18002436e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024373  mov     rax, [rbp+57h+application.ft]
0x180024377  test    rax, rax
0x18002437a  jz      short loc_180024388
0x18002437c  mov     rax, [rax]
0x18002437f  lea     rcx, [rbp+57h+application]
0x180024383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024388  mov     rcx, [rbp+57h+var_8]
0x18002438c  xor     rcx, rsp; StackCookie
0x18002438f  call    __security_check_cookie
0x180024394  mov     rdi, [rsp+100h+arg_0]
0x18002439c  add     rsp, 100h
0x1800243a3  pop     rbp
0x1800243a4  retn
```
