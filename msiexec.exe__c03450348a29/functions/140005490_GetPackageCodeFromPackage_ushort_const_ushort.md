# GetPackageCodeFromPackage(ushort const *,ushort *)

- ea: `0x140005490`
- end: `0x14000579a`
- name: `?GetPackageCodeFromPackage@@YAIPEBGPEAG@Z`
- size: `778`
- prototype: `unsigned int(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006e10`

## callees

- `0x140005490`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140005731`
- `KERNEL32!MultiByteToWideChar` at `0x140005731`
- `ole32!StgOpenStorage` at `0x1400054db`
- `ole32!StgOpenStorage` at `0x1400054db`

## pseudocode

```c
__int64 __fastcall GetPackageCodeFromPackage(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  HRESULT v3; // ecx
  __int64 result; // rax
  char v5; // bl
  int v6; // eax
  int v7; // ecx
  int v8; // [rsp+40h] [rbp-29h] BYREF
  __int64 v9; // [rsp+48h] [rbp-21h] BYREF
  int v10; // [rsp+50h] [rbp-19h] BYREF
  __int64 v11; // [rsp+58h] [rbp-11h]
  unsigned int v12; // [rsp+60h] [rbp-9h] BYREF
  int v13; // [rsp+64h] [rbp-5h] BYREF
  int v14; // [rsp+68h] [rbp-1h] BYREF
  IStorage *ppstgOpen; // [rsp+70h] [rbp+7h] BYREF
  int v16; // [rsp+78h] [rbp+Fh] BYREF
  CHAR MultiByteStr[40]; // [rsp+80h] [rbp+17h] BYREF

  ppstgOpen = 0;
  v9 = 0;
  v3 = StgOpenStorage(a1, 0, 0x20u, 0, 0, &ppstgOpen);
  if ( v3 >= 0 )
  {
    if ( ((int (__fastcall *)(IStorage *, void *, _QWORD, __int64, _DWORD, __int64 *))ppstgOpen->lpVtbl->OpenStream)(
           ppstgOpen,
           &unk_14000CC48,
           0,
           16,
           0,
           &v9) >= 0 )
    {
      v8 = 0;
      v11 = 44;
      v5 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, 44, 0, 0) >= 0 )
      {
        v12 = 0;
        v10 = 0;
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, unsigned int *, __int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v12, 4, &v8) >= 0
          && v8 == 4 )
        {
          v11 = v12;
          if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, v12, 0, 0) >= 0
            && (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v10, 4, &v8) >= 0
            && v8 == 4
            && (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v16, 4, &v8) >= 0
            && v8 == 4 )
          {
            v6 = v10;
            v7 = 0;
            v13 = 0;
            v14 = 0;
            while ( v6 )
            {
              if ( v7 == 9 )
                goto LABEL_24;
              if ( (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v13, 4, &v8) < 0
                || v8 != 4
                || (*(int (__fastcall **)(__int64, int *, __int64, int *))(*(_QWORD *)v9 + 24LL))(v9, &v14, 4, &v8) < 0
                || v8 != 4 )
              {
                goto LABEL_29;
              }
              v7 = v13;
              v6 = v10 - 8;
              v10 -= 8;
            }
            if ( v7 != 9 )
              goto LABEL_29;
LABEL_24:
            v11 = v14 + 8 + v12;
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, v11, 0, 0) >= 0
              && (*(int (__fastcall **)(__int64, CHAR *, __int64, int *))(*(_QWORD *)v9 + 24LL))(
                   v9,
                   MultiByteStr,
                   38,
                   &v8) >= 0
              && v8 == 38 )
            {
              MultiByteStr[38] = 0;
              if ( MultiByteToWideChar(0, 0, MultiByteStr, 39, a2, 39) )
              {
                a2[38] = 0;
                v5 = 1;
              }
            }
          }
        }
      }
LABEL_29:
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
      return v5 == 0 ? 0x654 : 0;
    }
    else
    {
      ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
      return 1620;
    }
  }
  else
  {
    result = 1619;
    if ( v3 == -2147287038 )
      return 2;
  }
  return result;
}

```

## disassembly

```asm
0x140005490  mov     [rsp-8+arg_10], rbx
0x140005495  mov     [rsp-8+arg_18], rsi
0x14000549a  push    rbp
0x14000549b  push    rdi
0x14000549c  push    r14
0x14000549e  lea     rbp, [rsp-47h]
0x1400054a3  sub     rsp, 0B0h
0x1400054aa  mov     rax, cs:__security_cookie
0x1400054b1  xor     rax, rsp
0x1400054b4  mov     [rbp+57h+var_18], rax
0x1400054b8  xor     esi, esi
0x1400054ba  lea     rax, [rbp+57h+var_50]
0x1400054be  mov     rdi, rdx
0x1400054c1  mov     [rsp+0C0h+ppstgOpen], rax; ppstgOpen
0x1400054c6  xor     r9d, r9d; snbExclude
0x1400054c9  mov     [rbp+57h+var_50], rsi
0x1400054cd  xor     edx, edx; pstgPriority
0x1400054cf  mov     [rbp+57h+var_78], rsi
0x1400054d3  lea     r8d, [rsi+20h]; grfMode
0x1400054d7  mov     [rsp+0C0h+reserved], esi; reserved
0x1400054db  call    cs:__imp_StgOpenStorage
0x1400054e1  mov     ecx, eax
0x1400054e3  test    eax, eax
0x1400054e5  jns     short loc_1400054FD
0x1400054e7  cmp     ecx, 80030002h
0x1400054ed  lea     edx, [rsi+2]
0x1400054f0  mov     eax, 653h
0x1400054f5  cmovz   eax, edx
0x1400054f8  jmp     loc_140005776
0x1400054fd  mov     rcx, [rbp+57h+var_50]
0x140005501  lea     rdx, [rbp+57h+var_78]
0x140005505  mov     [rsp+0C0h+ppstgOpen], rdx
0x14000550a  mov     r9d, 10h
0x140005510  xor     r8d, r8d
0x140005513  mov     [rsp+0C0h+reserved], esi
0x140005517  lea     rdx, unk_14000CC48
0x14000551e  mov     rax, [rcx]
0x140005521  mov     rax, [rax+20h]
0x140005525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000552a  test    eax, eax
0x14000552c  jns     short loc_140005548
0x14000552e  mov     rcx, [rbp+57h+var_50]
0x140005532  mov     rax, [rcx]
0x140005535  mov     rax, [rax+10h]
0x140005539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000553e  mov     eax, 654h
0x140005543  jmp     loc_140005776
0x140005548  mov     rcx, [rbp+57h+var_78]
0x14000554c  xor     r9d, r9d
0x14000554f  mov     [rbp+57h+var_80], esi
0x140005552  xor     r8d, r8d
0x140005555  mov     [rbp+57h+var_68], 2Ch ; ','
0x14000555d  mov     bl, sil
0x140005560  mov     rdx, [rbp+57h+var_68]
0x140005564  mov     rax, [rcx]
0x140005567  mov     rax, [rax+28h]
0x14000556b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005570  test    eax, eax
0x140005572  js      loc_140005741
0x140005578  mov     rcx, [rbp+57h+var_78]
0x14000557c  lea     r9, [rbp+57h+var_80]
0x140005580  mov     [rbp+57h+var_60], esi
0x140005583  lea     rdx, [rbp+57h+var_60]
0x140005587  mov     [rbp+57h+var_70], esi
0x14000558a  mov     r14d, 4
0x140005590  mov     [rbp+57h+var_48], esi
0x140005593  mov     r8d, r14d
0x140005596  mov     rax, [rcx]
0x140005599  mov     rax, [rax+18h]
0x14000559d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055a2  test    eax, eax
0x1400055a4  js      loc_140005741
0x1400055aa  cmp     [rbp+57h+var_80], r14d
0x1400055ae  jnz     loc_140005741
0x1400055b4  mov     eax, [rbp+57h+var_60]
0x1400055b7  xor     r9d, r9d
0x1400055ba  mov     rcx, [rbp+57h+var_78]
0x1400055be  xor     r8d, r8d
0x1400055c1  mov     dword ptr [rbp+57h+var_68], eax
0x1400055c4  mov     dword ptr [rbp+57h+var_68+4], esi
0x1400055c7  mov     rdx, [rbp+57h+var_68]
0x1400055cb  mov     rax, [rcx]
0x1400055ce  mov     rax, [rax+28h]
0x1400055d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055d7  test    eax, eax
0x1400055d9  js      loc_140005741
0x1400055df  mov     rcx, [rbp+57h+var_78]
0x1400055e3  lea     r9, [rbp+57h+var_80]
0x1400055e7  mov     r8d, r14d
0x1400055ea  lea     rdx, [rbp+57h+var_70]
0x1400055ee  mov     rax, [rcx]
0x1400055f1  mov     rax, [rax+18h]
0x1400055f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055fa  test    eax, eax
0x1400055fc  js      loc_140005741
0x140005602  cmp     [rbp+57h+var_80], r14d
0x140005606  jnz     loc_140005741
0x14000560c  mov     rcx, [rbp+57h+var_78]
0x140005610  lea     r9, [rbp+57h+var_80]
0x140005614  mov     r8d, r14d
0x140005617  lea     rdx, [rbp+57h+var_48]
0x14000561b  mov     rax, [rcx]
0x14000561e  mov     rax, [rax+18h]
0x140005622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005627  test    eax, eax
0x140005629  js      loc_140005741
0x14000562f  cmp     [rbp+57h+var_80], r14d
0x140005633  jnz     loc_140005741
0x140005639  mov     eax, [rbp+57h+var_70]
0x14000563c  mov     ecx, esi
0x14000563e  mov     [rbp+57h+var_5C], ecx
0x140005641  mov     [rbp+57h+var_58], esi
0x140005644  test    eax, eax
0x140005646  jz      short loc_1400056B5
0x140005648  cmp     ecx, 9
0x14000564b  jz      short loc_1400056BE
0x14000564d  mov     rcx, [rbp+57h+var_78]
0x140005651  lea     r9, [rbp+57h+var_80]
0x140005655  mov     r8d, r14d
0x140005658  lea     rdx, [rbp+57h+var_5C]
0x14000565c  mov     rax, [rcx]
0x14000565f  mov     rax, [rax+18h]
0x140005663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005668  test    eax, eax
0x14000566a  js      loc_140005741
0x140005670  cmp     [rbp+57h+var_80], r14d
0x140005674  jnz     loc_140005741
0x14000567a  mov     rcx, [rbp+57h+var_78]
0x14000567e  lea     r9, [rbp+57h+var_80]
0x140005682  mov     r8d, r14d
0x140005685  lea     rdx, [rbp+57h+var_58]
0x140005689  mov     rax, [rcx]
0x14000568c  mov     rax, [rax+18h]
0x140005690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005695  test    eax, eax
0x140005697  js      loc_140005741
0x14000569d  cmp     [rbp+57h+var_80], r14d
0x1400056a1  jnz     loc_140005741
0x1400056a7  mov     eax, [rbp+57h+var_70]
0x1400056aa  mov     ecx, [rbp+57h+var_5C]
0x1400056ad  sub     eax, 8
0x1400056b0  mov     [rbp+57h+var_70], eax
0x1400056b3  jmp     short loc_140005644
0x1400056b5  cmp     ecx, 9
0x1400056b8  jnz     loc_140005741
0x1400056be  mov     eax, [rbp+57h+var_58]
0x1400056c1  xor     r9d, r9d
0x1400056c4  mov     ecx, [rbp+57h+var_60]
0x1400056c7  add     eax, 8
0x1400056ca  add     ecx, eax
0x1400056cc  mov     dword ptr [rbp+57h+var_68+4], esi
0x1400056cf  mov     dword ptr [rbp+57h+var_68], ecx
0x1400056d2  xor     r8d, r8d
0x1400056d5  mov     rcx, [rbp+57h+var_78]
0x1400056d9  mov     rdx, [rbp+57h+var_68]
0x1400056dd  mov     rax, [rcx]
0x1400056e0  mov     rax, [rax+28h]
0x1400056e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056e9  test    eax, eax
0x1400056eb  js      short loc_140005741
0x1400056ed  mov     rcx, [rbp+57h+var_78]
0x1400056f1  lea     r9, [rbp+57h+var_80]
0x1400056f5  mov     r8d, 26h ; '&'
0x1400056fb  lea     rdx, [rbp+57h+MultiByteStr]
0x1400056ff  mov     rax, [rcx]
0x140005702  mov     rax, [rax+18h]
0x140005706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000570b  test    eax, eax
0x14000570d  js      short loc_140005741
0x14000570f  cmp     [rbp+57h+var_80], 26h ; '&'
0x140005713  jnz     short loc_140005741
0x140005715  mov     r9d, 27h ; '''; cbMultiByte
0x14000571b  mov     [rbp+57h+var_1A], sil
0x14000571f  mov     dword ptr [rsp+0C0h+ppstgOpen], r9d; cchWideChar
0x140005724  lea     r8, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x140005728  xor     edx, edx; dwFlags
0x14000572a  mov     qword ptr [rsp+0C0h+reserved], rdi; lpWideCharStr
0x14000572f  xor     ecx, ecx; CodePage
0x140005731  call    cs:__imp_MultiByteToWideChar
0x140005737  test    eax, eax
0x140005739  jz      short loc_140005741
0x14000573b  mov     [rdi+4Ch], si
0x14000573f  mov     bl, 1
0x140005741  mov     rcx, [rbp+57h+var_78]
0x140005745  test    rcx, rcx
0x140005748  jz      short loc_140005756
0x14000574a  mov     rax, [rcx]
0x14000574d  mov     rax, [rax+10h]
0x140005751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005756  mov     rcx, [rbp+57h+var_50]
0x14000575a  test    rcx, rcx
0x14000575d  jz      short loc_14000576B
0x14000575f  mov     rax, [rcx]
0x140005762  mov     rax, [rax+10h]
0x140005766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000576b  neg     bl
0x14000576d  sbb     eax, eax
0x14000576f  not     eax
0x140005771  and     eax, 654h
0x140005776  mov     rcx, [rbp+57h+var_18]
0x14000577a  xor     rcx, rsp; StackCookie
0x14000577d  call    __security_check_cookie
0x140005782  lea     r11, [rsp+0C0h+var_10]
0x14000578a  mov     rbx, [r11+30h]
0x14000578e  mov     rsi, [r11+38h]
0x140005792  mov     rsp, r11
0x140005795  pop     r14
0x140005797  pop     rdi
0x140005798  pop     rbp
0x140005799  retn
```
