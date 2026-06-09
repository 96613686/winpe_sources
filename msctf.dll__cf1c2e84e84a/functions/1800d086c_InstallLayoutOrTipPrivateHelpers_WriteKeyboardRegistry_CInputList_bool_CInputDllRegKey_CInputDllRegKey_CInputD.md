# InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(CInputList &,bool,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)

- ea: `0x1800d086c`
- end: `0x1800d0a8c`
- name: `?WriteKeyboardRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@_NAEAVCInputDllRegKey@@22@Z`
- size: `544`
- prototype: `void __usercall(struct CInputList *@<rcx>, bool@<dl>, struct CInputDllRegKey *@<r8>, struct CInputDllRegKey *@<r9>, struct CInputDllRegKey *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180097ad0`

## callees

- `0x18000fac0`
- `0x1800cd5f4`
- `0x1800cecd8`
- `0x1800cffc0`
- `0x1800d0684`
- `0x1800d086c`
- `0x1800d0a94`
- `0x180106a60`

## import_xrefs

- `USER32!LoadKeyboardLayoutW` at `0x1800d097d`
- `USER32!LoadKeyboardLayoutW` at `0x1800d097d`
- `USER32!UnloadKeyboardLayout` at `0x1800d0a49`
- `USER32!UnloadKeyboardLayout` at `0x1800d0a49`
- `USER32!SystemParametersInfoW` at `0x1800d09a3`
- `USER32!SystemParametersInfoW` at `0x1800d09c7`
- `USER32!SystemParametersInfoW` at `0x1800d09a3`
- `USER32!SystemParametersInfoW` at `0x1800d09c7`

## pseudocode

```c
void __fastcall InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(
        struct CInputList *a1,
        char a2,
        struct CInputDllRegKey *a3,
        struct CInputDllRegKey *a4,
        struct CInputDllRegKey *a5)
{
  int v9; // edx
  __int64 *v10; // r15
  unsigned __int16 *v11; // rbx
  unsigned int v12; // esi
  unsigned int *v13; // rdi
  unsigned int v14; // ebp
  __int64 v15; // r9
  HKL KeyboardLayoutW; // rax
  bool v17; // r8
  __int64 v18; // rax
  unsigned int i; // ebx
  unsigned int v20; // edx
  HKL HKLFromLayout; // rax
  HKL pvParam; // [rsp+20h] [rbp-78h] BYREF
  HKL v23; // [rsp+28h] [rbp-70h] BYREF
  struct CInputDllRegKey *v24; // [rsp+30h] [rbp-68h]
  struct CInputDllRegKey *v25; // [rsp+38h] [rbp-60h]
  WCHAR pwszKLID[8]; // [rsp+40h] [rbp-58h] BYREF
  __int16 v27; // [rsp+50h] [rbp-48h]

  v25 = a5;
  v24 = a4;
  CInputDllRegKey::RecurseDeleteKey(a3, &lParam, 0);
  CInputDllRegKey::RecurseDeleteKey(a4, &lParam, 0);
  v9 = *(_DWORD *)a1;
  v10 = (__int64 *)((char *)a1 + 8);
  if ( *(_DWORD *)a1 && (v11 = (unsigned __int16 *)*v10) != 0 )
  {
    v12 = 0;
    v13 = (unsigned int *)((char *)a1 + 4);
    v14 = 1;
    do
    {
      if ( v12 >= *v13 )
        break;
      if ( *((_DWORD *)v11 + 1) )
      {
        if ( *((_BYTE *)v11 + 16) )
        {
          if ( *((_DWORD *)v11 + 1) != *v11 )
            InstallLayoutOrTipPrivateHelpers::CalculateKeyboardSubstituteLayoutForEntry(
              v12,
              (struct InputContainer *)v11,
              a1);
          InstallLayoutOrTipPrivateHelpers::WriteKeyboardToRegistry((struct InputContainer *)v11, v14, a3, v24);
          if ( a2 )
          {
            v15 = *((unsigned int *)v11 + 2);
            v27 = 0;
            *(_OWORD *)pwszKLID = 0;
            if ( !(_DWORD)v15 )
              v15 = *((unsigned int *)v11 + 1);
            StringCchPrintfW(pwszKLID, 9u, L"%08x", v15);
            KeyboardLayoutW = LoadKeyboardLayoutW(pwszKLID, 0x82u);
            if ( v14 == 1 )
            {
              v23 = KeyboardLayoutW;
              pvParam = 0;
              SystemParametersInfoW(0x59u, 0, &pvParam, 0);
              if ( v23 )
              {
                if ( v23 != pvParam )
                  SystemParametersInfoW(0x5Au, 0, &v23, 0);
              }
            }
          }
          ++v14;
        }
        v17 = *((_BYTE *)v11 + 18) && *((_BYTE *)v11 + 16);
        InstallLayoutOrTipPrivateHelpers::WriteHiddenDummyLayoutRegistry(*v11, *((_DWORD *)v11 + 1), v17, v25);
      }
      v9 = *(_DWORD *)a1;
      if ( ++v12 >= *(_DWORD *)a1 )
        break;
      v11 = (unsigned __int16 *)(*((_QWORD *)a1 + 1) + 700LL * v12);
    }
    while ( v11 );
  }
  else
  {
    v13 = (unsigned int *)((char *)a1 + 4);
  }
  if ( a2 )
  {
    if ( v9 )
    {
      v18 = *v10;
      for ( i = 0; v18; v18 = 700LL * i + *v10 )
      {
        if ( i >= *v13 )
          break;
        v20 = *(_DWORD *)(v18 + 4);
        if ( v20 )
        {
          if ( !*(_BYTE *)(v18 + 16) )
          {
            HKLFromLayout = GetHKLFromLayout(*(_WORD *)v18, v20);
            if ( HKLFromLayout )
              UnloadKeyboardLayout(HKLFromLayout);
          }
        }
        if ( ++i >= *(_DWORD *)a1 )
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x1800d086c  mov     [rsp+arg_8], rbx
0x1800d0871  push    rbp
0x1800d0872  push    rsi
0x1800d0873  push    rdi
0x1800d0874  push    r12
0x1800d0876  push    r13
0x1800d0878  push    r14
0x1800d087a  push    r15
0x1800d087c  sub     rsp, 60h
0x1800d0880  mov     rax, cs:__security_cookie
0x1800d0887  xor     rax, rsp
0x1800d088a  mov     [rsp+98h+var_40], rax
0x1800d088f  mov     rax, [rsp+98h+arg_20]
0x1800d0897  mov     r13, r8
0x1800d089a  mov     rbx, r9
0x1800d089d  mov     [rsp+98h+var_60], rax
0x1800d08a2  mov     r12b, dl
0x1800d08a5  mov     [rsp+98h+var_68], rbx
0x1800d08aa  mov     r14, rcx
0x1800d08ad  lea     rdx, lParam; unsigned __int16 *
0x1800d08b4  mov     rcx, r13; this
0x1800d08b7  xor     r8d, r8d; int
0x1800d08ba  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x1800d08bf  xor     r8d, r8d; int
0x1800d08c2  lea     rdx, lParam; unsigned __int16 *
0x1800d08c9  mov     rcx, rbx; this
0x1800d08cc  call    ?RecurseDeleteKey@CInputDllRegKey@@QEAAJPEBGH@Z; CInputDllRegKey::RecurseDeleteKey(ushort const *,int)
0x1800d08d1  mov     edx, [r14]
0x1800d08d4  lea     r15, [r14+8]
0x1800d08d8  test    edx, edx
0x1800d08da  jz      loc_1800D0A11
0x1800d08e0  mov     rbx, [r15]
0x1800d08e3  test    rbx, rbx
0x1800d08e6  jz      loc_1800D0A11
0x1800d08ec  xor     esi, esi
0x1800d08ee  lea     rdi, [r14+4]
0x1800d08f2  lea     ebp, [rsi+1]
0x1800d08f5  cmp     esi, [rdi]
0x1800d08f7  jnb     loc_1800D0A15
0x1800d08fd  cmp     dword ptr [rbx+4], 0
0x1800d0901  jz      loc_1800D09F3
0x1800d0907  cmp     byte ptr [rbx+10h], 0
0x1800d090b  jz      loc_1800D09CF
0x1800d0911  movzx   eax, word ptr [rbx]
0x1800d0914  cmp     [rbx+4], eax
0x1800d0917  jz      short loc_1800D0926
0x1800d0919  mov     r8, r14; struct CInputList *
0x1800d091c  mov     rdx, rbx; struct InputContainer *
0x1800d091f  mov     ecx, esi; unsigned int
0x1800d0921  call    ?CalculateKeyboardSubstituteLayoutForEntry@InstallLayoutOrTipPrivateHelpers@@SAXKPEAUInputContainer@@AEAVCInputList@@@Z; InstallLayoutOrTipPrivateHelpers::CalculateKeyboardSubstituteLayoutForEntry(ulong,InputContainer *,CInputList &)
0x1800d0926  mov     r9, [rsp+98h+var_68]; struct CInputDllRegKey *
0x1800d092b  mov     r8, r13; struct CInputDllRegKey *
0x1800d092e  mov     edx, ebp; unsigned int
0x1800d0930  mov     rcx, rbx; struct InputContainer *
0x1800d0933  call    ?WriteKeyboardToRegistry@InstallLayoutOrTipPrivateHelpers@@SAXPEAUInputContainer@@KAEAVCInputDllRegKey@@1@Z; InstallLayoutOrTipPrivateHelpers::WriteKeyboardToRegistry(InputContainer *,ulong,CInputDllRegKey &,CInputDllRegKey &)
0x1800d0938  test    r12b, r12b
0x1800d093b  jz      loc_1800D09CD
0x1800d0941  mov     r9d, [rbx+8]
0x1800d0945  xor     eax, eax
0x1800d0947  mov     [rsp+98h+var_48], ax
0x1800d094c  xorps   xmm0, xmm0
0x1800d094f  movups  xmmword ptr [rsp+98h+pwszKLID], xmm0
0x1800d0954  test    r9d, r9d
0x1800d0957  jnz     short loc_1800D095D
0x1800d0959  mov     r9d, [rbx+4]
0x1800d095d  lea     r8, a08x_1; "%08x"
0x1800d0964  mov     edx, 9; unsigned __int64
0x1800d0969  lea     rcx, [rsp+98h+pwszKLID]; unsigned __int16 *
0x1800d096e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d0973  mov     edx, 82h; Flags
0x1800d0978  lea     rcx, [rsp+98h+pwszKLID]; pwszKLID
0x1800d097d  call    cs:__imp_LoadKeyboardLayoutW
0x1800d0983  cmp     ebp, 1
0x1800d0986  jnz     short loc_1800D09CD
0x1800d0988  xor     r9d, r9d; fWinIni
0x1800d098b  mov     [rsp+98h+var_70], rax
0x1800d0990  lea     r8, [rsp+98h+pvParam]; pvParam
0x1800d0995  mov     [rsp+98h+pvParam], 0
0x1800d099e  xor     edx, edx; uiParam
0x1800d09a0  lea     ecx, [rbp+58h]; uiAction
0x1800d09a3  call    cs:__imp_SystemParametersInfoW
0x1800d09a9  mov     rax, [rsp+98h+var_70]
0x1800d09ae  test    rax, rax
0x1800d09b1  jz      short loc_1800D09CD
0x1800d09b3  cmp     rax, [rsp+98h+pvParam]
0x1800d09b8  jz      short loc_1800D09CD
0x1800d09ba  xor     r9d, r9d; fWinIni
0x1800d09bd  lea     r8, [rsp+98h+var_70]; pvParam
0x1800d09c2  xor     edx, edx; uiParam
0x1800d09c4  lea     ecx, [rbp+59h]; uiAction
0x1800d09c7  call    cs:__imp_SystemParametersInfoW
0x1800d09cd  inc     ebp
0x1800d09cf  cmp     byte ptr [rbx+12h], 0
0x1800d09d3  jz      short loc_1800D09E0
0x1800d09d5  cmp     byte ptr [rbx+10h], 0
0x1800d09d9  jz      short loc_1800D09E0
0x1800d09db  mov     r8b, 1
0x1800d09de  jmp     short loc_1800D09E3
0x1800d09e0  xor     r8d, r8d; bool
0x1800d09e3  mov     r9, [rsp+98h+var_60]; struct CInputDllRegKey *
0x1800d09e8  mov     edx, [rbx+4]; unsigned int
0x1800d09eb  movzx   ecx, word ptr [rbx]; unsigned __int16
0x1800d09ee  call    ?WriteHiddenDummyLayoutRegistry@InstallLayoutOrTipPrivateHelpers@@SAXGK_NAEAVCInputDllRegKey@@@Z; InstallLayoutOrTipPrivateHelpers::WriteHiddenDummyLayoutRegistry(ushort,ulong,bool,CInputDllRegKey &)
0x1800d09f3  mov     edx, [r14]
0x1800d09f6  inc     esi
0x1800d09f8  cmp     esi, edx
0x1800d09fa  jnb     short loc_1800D0A15
0x1800d09fc  mov     eax, esi
0x1800d09fe  imul    rbx, rax, 2BCh
0x1800d0a05  add     rbx, [r14+8]
0x1800d0a09  jnz     loc_1800D08F5
0x1800d0a0f  jmp     short loc_1800D0A15
0x1800d0a11  lea     rdi, [r14+4]
0x1800d0a15  test    r12b, r12b
0x1800d0a18  jz      short loc_1800D0A67
0x1800d0a1a  test    edx, edx
0x1800d0a1c  jz      short loc_1800D0A67
0x1800d0a1e  mov     rax, [r15]
0x1800d0a21  xor     ebx, ebx
0x1800d0a23  test    rax, rax
0x1800d0a26  jz      short loc_1800D0A67
0x1800d0a28  cmp     ebx, [rdi]
0x1800d0a2a  jnb     short loc_1800D0A67
0x1800d0a2c  mov     edx, [rax+4]; unsigned int
0x1800d0a2f  test    edx, edx
0x1800d0a31  jz      short loc_1800D0A4F
0x1800d0a33  cmp     byte ptr [rax+10h], 0
0x1800d0a37  jnz     short loc_1800D0A4F
0x1800d0a39  movzx   ecx, word ptr [rax]; unsigned __int16
0x1800d0a3c  call    ?GetHKLFromLayout@@YAPEAUHKL__@@GK@Z; GetHKLFromLayout(ushort,ulong)
0x1800d0a41  test    rax, rax
0x1800d0a44  jz      short loc_1800D0A4F
0x1800d0a46  mov     rcx, rax; hkl
0x1800d0a49  call    cs:__imp_UnloadKeyboardLayout
0x1800d0a4f  inc     ebx
0x1800d0a51  cmp     ebx, [r14]
0x1800d0a54  jnb     short loc_1800D0A67
0x1800d0a56  mov     eax, ebx
0x1800d0a58  imul    rcx, rax, 2BCh
0x1800d0a5f  mov     rax, [r15]
0x1800d0a62  add     rax, rcx
0x1800d0a65  jnz     short loc_1800D0A28
0x1800d0a67  mov     rcx, [rsp+98h+var_40]
0x1800d0a6c  xor     rcx, rsp; StackCookie
0x1800d0a6f  call    __security_check_cookie
0x1800d0a74  mov     rbx, [rsp+98h+arg_8]
0x1800d0a7c  add     rsp, 60h
0x1800d0a80  pop     r15
0x1800d0a82  pop     r14
0x1800d0a84  pop     r13
0x1800d0a86  pop     r12
0x1800d0a88  pop     rdi
0x1800d0a89  pop     rsi
0x1800d0a8a  pop     rbp
0x1800d0a8b  retn
```
