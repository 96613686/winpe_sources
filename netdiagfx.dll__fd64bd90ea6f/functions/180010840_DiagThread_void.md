# DiagThread(void *)

- ea: `0x180010840`
- end: `0x180010b56`
- name: `?DiagThread@@YAKPEAX@Z`
- size: `790`
- prototype: `__int64 __fastcall(HRESULT *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010840`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001084f`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001084f`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180010b43`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180010b43`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180010b35`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180010b35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DiagThread(HRESULT *Parameter)
{
  HRESULT v2; // eax
  int v3; // edx
  int v4; // edi
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  HRESULT ClassObject; // eax
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, _QWORD); // rax
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  __int64 (*v22)(void); // rax
  __int64 *v23; // rcx
  __int64 v24; // rax
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int128 v32; // [rsp+30h] [rbp-18h] BYREF

  v2 = CoEnableCallCancellation(0);
  v3 = Parameter[4];
  v4 = v2;
  if ( v3 <= 13 )
  {
    if ( v3 == 13 )
    {
      ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 112LL))(
                      *((_QWORD *)Parameter + 3),
                      (unsigned int)Parameter[8],
                      *((_QWORD *)Parameter + 5),
                      *((_QWORD *)Parameter + 6));
      goto LABEL_62;
    }
    if ( v3 > 7 )
    {
      v13 = v3 - 8;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 1 )
              {
                ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3)
                                                                                        + 104LL))(
                                *((_QWORD *)Parameter + 3),
                                (unsigned int)Parameter[8],
                                *((_QWORD *)Parameter + 5),
                                *((_QWORD *)Parameter + 6));
                goto LABEL_62;
              }
              goto LABEL_55;
            }
            ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 96LL))(
                            *((_QWORD *)Parameter + 3),
                            *((_QWORD *)Parameter + 4),
                            *((_QWORD *)Parameter + 5),
                            *((_QWORD *)Parameter + 6));
          }
          else
          {
            ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 88LL))(
                            *((_QWORD *)Parameter + 3),
                            *((_QWORD *)Parameter + 4),
                            *((_QWORD *)Parameter + 5));
          }
        }
        else
        {
          ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 80LL))(
                          *((_QWORD *)Parameter + 3),
                          *((_QWORD *)Parameter + 4),
                          *((_QWORD *)Parameter + 5));
        }
      }
      else
      {
        ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 72LL))(
                        *((_QWORD *)Parameter + 3),
                        *((_QWORD *)Parameter + 4),
                        *((_QWORD *)Parameter + 5));
      }
LABEL_62:
      *Parameter = ClassObject;
      goto LABEL_63;
    }
    if ( v3 == 7 )
    {
      ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 64LL))(
                      *((_QWORD *)Parameter + 3),
                      *((_QWORD *)Parameter + 4),
                      *((_QWORD *)Parameter + 5));
      goto LABEL_62;
    }
    v5 = v3 - 1;
    if ( !v5 )
    {
      ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 24LL))(
                      *((_QWORD *)Parameter + 3),
                      (unsigned int)Parameter[8],
                      *((_QWORD *)Parameter + 5));
      goto LABEL_62;
    }
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( !v8 )
        {
          ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 40LL))(
                          *((_QWORD *)Parameter + 3),
                          *((_QWORD *)Parameter + 4),
                          *((_QWORD *)Parameter + 5));
          goto LABEL_62;
        }
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
          {
            ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3)
                                                                                            + 56LL))(
                            *((_QWORD *)Parameter + 3),
                            *((_QWORD *)Parameter + 4),
                            *((_QWORD *)Parameter + 5),
                            *((_QWORD *)Parameter + 6),
                            *((_QWORD *)Parameter + 7));
            goto LABEL_62;
          }
LABEL_55:
          *Parameter = -2147467263;
          goto LABEL_63;
        }
        ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3)
                                                                                        + 48LL))(
                        *((_QWORD *)Parameter + 3),
                        *((_QWORD *)Parameter + 4),
                        *((_QWORD *)Parameter + 5),
                        *((_QWORD *)Parameter + 6),
                        *((_QWORD *)Parameter + 7));
      }
      else
      {
        ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 24LL))(
                        *((_QWORD *)Parameter + 3),
                        *((_QWORD *)Parameter + 4),
                        *((_QWORD *)Parameter + 5));
      }
      goto LABEL_62;
    }
    v11 = *((_QWORD *)Parameter + 3);
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 32LL);
LABEL_18:
    ClassObject = v12(v11, *((_QWORD *)Parameter + 4));
    goto LABEL_62;
  }
  if ( v3 <= 20 )
  {
    if ( v3 == 20 )
    {
      ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3)
                                                                                      + 24LL))(
                      *((_QWORD *)Parameter + 3),
                      (unsigned int)Parameter[8],
                      *((_QWORD *)Parameter + 5),
                      *((_QWORD *)Parameter + 6),
                      *((_QWORD *)Parameter + 7));
      goto LABEL_62;
    }
    v17 = v3 - 14;
    if ( !v17 )
    {
      v11 = *((_QWORD *)Parameter + 3);
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 120LL);
      goto LABEL_18;
    }
    v18 = v17 - 1;
    if ( !v18 )
    {
      v23 = (__int64 *)*((_QWORD *)Parameter + 3);
      v24 = *v23;
      v32 = *((_OWORD *)Parameter + 2);
      ClassObject = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v24 + 128))(v23, &v32);
      goto LABEL_62;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v11 = *((_QWORD *)Parameter + 3);
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 136LL);
      goto LABEL_18;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      ClassObject = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)Parameter + 3) + 144LL))(
                      *((_QWORD *)Parameter + 3),
                      *((_QWORD *)Parameter + 4),
                      *((_QWORD *)Parameter + 5));
      goto LABEL_62;
    }
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( v21 != 1 )
        goto LABEL_55;
      v22 = *(__int64 (**)(void))(**((_QWORD **)Parameter + 3) + 160LL);
    }
    else
    {
      v22 = *(__int64 (**)(void))(**((_QWORD **)Parameter + 3) + 152LL);
    }
LABEL_43:
    ClassObject = v22();
    goto LABEL_62;
  }
  v25 = v3 - 21;
  if ( !v25 )
  {
    ClassObject = CoGetClassObject(
                    (const IID *const)Parameter + 2,
                    4u,
                    0,
                    (const IID *const)Parameter + 3,
                    *((LPVOID **)Parameter + 8));
    goto LABEL_62;
  }
  v26 = v25 - 1;
  if ( v26 && (v27 = v26 - 1) != 0 )
  {
    v28 = v27 - 1;
    if ( v28 )
    {
      if ( v28 != 1 )
        goto LABEL_55;
      v22 = *(__int64 (**)(void))(**((_QWORD **)Parameter + 3) + 40LL);
      goto LABEL_43;
    }
    v29 = *((_QWORD *)Parameter + 3);
    if ( v29 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 32LL))(v29, *((_QWORD *)Parameter + 4));
  }
  else
  {
    v30 = *((_QWORD *)Parameter + 3);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
LABEL_63:
  if ( v4 >= 0 )
    CoDisableCallCancellation(0);
  return 0;
}

```

## disassembly

```asm
0x180010840  mov     [rsp+arg_0], rbx
0x180010845  push    rdi
0x180010846  sub     rsp, 40h
0x18001084a  mov     rbx, rcx
0x18001084d  xor     ecx, ecx; pReserved
0x18001084f  call    cs:__imp_CoEnableCallCancellation
0x180010855  mov     edx, [rbx+10h]
0x180010858  mov     edi, eax
0x18001085a  cmp     edx, 0Dh
0x18001085d  jg      loc_1800109DC
0x180010863  jz      loc_1800109CF
0x180010869  cmp     edx, 7
0x18001086c  jg      loc_180010941
0x180010872  jz      loc_180010934
0x180010878  sub     edx, 1
0x18001087b  jz      loc_180010918
0x180010881  sub     edx, 1
0x180010884  jz      short loc_1800108FF
0x180010886  sub     edx, 1
0x180010889  jz      short loc_1800108F2
0x18001088b  sub     edx, 1
0x18001088e  jz      short loc_1800108D5
0x180010890  sub     edx, 1
0x180010893  jz      short loc_1800108C8
0x180010895  cmp     edx, 1
0x180010898  jnz     loc_180010AD3
0x18001089e  mov     rcx, [rbx+18h]
0x1800108a2  mov     rax, [rcx]
0x1800108a5  mov     rax, [rax+38h]
0x1800108a9  mov     rdx, [rbx+38h]
0x1800108ad  mov     r8, [rbx+28h]
0x1800108b1  mov     r9, [rbx+30h]
0x1800108b5  mov     [rsp+48h+ppv], rdx
0x1800108ba  mov     rdx, [rbx+20h]
0x1800108be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c3  jmp     loc_180010B3B
0x1800108c8  mov     rcx, [rbx+18h]
0x1800108cc  mov     rax, [rcx]
0x1800108cf  mov     rax, [rax+30h]
0x1800108d3  jmp     short loc_1800108A9
0x1800108d5  mov     rcx, [rbx+18h]
0x1800108d9  mov     rax, [rcx]
0x1800108dc  mov     rax, [rax+28h]
0x1800108e0  mov     r8, [rbx+28h]
0x1800108e4  mov     rdx, [rbx+20h]
0x1800108e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ed  jmp     loc_180010B3B
0x1800108f2  mov     rcx, [rbx+18h]
0x1800108f6  mov     rax, [rcx]
0x1800108f9  mov     rax, [rax+18h]
0x1800108fd  jmp     short loc_1800108E0
0x1800108ff  mov     rcx, [rbx+18h]
0x180010903  mov     rax, [rcx]
0x180010906  mov     rax, [rax+20h]
0x18001090a  mov     rdx, [rbx+20h]
0x18001090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010913  jmp     loc_180010B3B
0x180010918  mov     rcx, [rbx+18h]
0x18001091c  mov     r8, [rbx+28h]
0x180010920  mov     edx, [rbx+20h]
0x180010923  mov     rax, [rcx]
0x180010926  mov     rax, [rax+18h]
0x18001092a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001092f  jmp     loc_180010B3B
0x180010934  mov     rcx, [rbx+18h]
0x180010938  mov     rax, [rcx]
0x18001093b  mov     rax, [rax+40h]
0x18001093f  jmp     short loc_1800108E0
0x180010941  sub     edx, 8
0x180010944  jz      short loc_1800109BF
0x180010946  sub     edx, 1
0x180010949  jz      short loc_1800109AF
0x18001094b  sub     edx, 1
0x18001094e  jz      short loc_18001099F
0x180010950  sub     edx, 1
0x180010953  jz      short loc_18001097E
0x180010955  cmp     edx, 1
0x180010958  jnz     loc_180010AD3
0x18001095e  mov     rcx, [rbx+18h]
0x180010962  mov     rax, [rcx]
0x180010965  mov     rax, [rax+68h]
0x180010969  mov     edx, [rbx+20h]
0x18001096c  mov     r8, [rbx+28h]
0x180010970  mov     r9, [rbx+30h]
0x180010974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010979  jmp     loc_180010B3B
0x18001097e  mov     rcx, [rbx+18h]
0x180010982  mov     r9, [rbx+30h]
0x180010986  mov     r8, [rbx+28h]
0x18001098a  mov     rdx, [rbx+20h]
0x18001098e  mov     rax, [rcx]
0x180010991  mov     rax, [rax+60h]
0x180010995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099a  jmp     loc_180010B3B
0x18001099f  mov     rcx, [rbx+18h]
0x1800109a3  mov     rax, [rcx]
0x1800109a6  mov     rax, [rax+58h]
0x1800109aa  jmp     loc_1800108E0
0x1800109af  mov     rcx, [rbx+18h]
0x1800109b3  mov     rax, [rcx]
0x1800109b6  mov     rax, [rax+50h]
0x1800109ba  jmp     loc_1800108E0
0x1800109bf  mov     rcx, [rbx+18h]
0x1800109c3  mov     rax, [rcx]
0x1800109c6  mov     rax, [rax+48h]
0x1800109ca  jmp     loc_1800108E0
0x1800109cf  mov     rcx, [rbx+18h]
0x1800109d3  mov     rax, [rcx]
0x1800109d6  mov     rax, [rax+70h]
0x1800109da  jmp     short loc_180010969
0x1800109dc  cmp     edx, 14h
0x1800109df  jg      loc_180010ABA
0x1800109e5  jz      loc_180010A91
0x1800109eb  sub     edx, 0Eh
0x1800109ee  jz      loc_180010A81
0x1800109f4  sub     edx, 1
0x1800109f7  jz      short loc_180010A5F
0x1800109f9  sub     edx, 1
0x1800109fc  jz      short loc_180010A4C
0x1800109fe  sub     edx, 1
0x180010a01  jz      short loc_180010A39
0x180010a03  sub     edx, 1
0x180010a06  jz      short loc_180010A29
0x180010a08  cmp     edx, 1
0x180010a0b  jnz     loc_180010AD3
0x180010a11  mov     rcx, [rbx+18h]
0x180010a15  mov     rax, [rcx]
0x180010a18  mov     rax, [rax+0A0h]
0x180010a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a24  jmp     loc_180010B3B
0x180010a29  mov     rcx, [rbx+18h]
0x180010a2d  mov     rax, [rcx]
0x180010a30  mov     rax, [rax+98h]
0x180010a37  jmp     short loc_180010A1F
0x180010a39  mov     rcx, [rbx+18h]
0x180010a3d  mov     rax, [rcx]
0x180010a40  mov     rax, [rax+90h]
0x180010a47  jmp     loc_1800108E0
0x180010a4c  mov     rcx, [rbx+18h]
0x180010a50  mov     rax, [rcx]
0x180010a53  mov     rax, [rax+88h]
0x180010a5a  jmp     loc_18001090A
0x180010a5f  mov     rcx, [rbx+18h]
0x180010a63  lea     rdx, [rsp+48h+var_18]
0x180010a68  movups  xmm0, xmmword ptr [rbx+20h]
0x180010a6c  mov     rax, [rcx]
0x180010a6f  movdqu  [rsp+48h+var_18], xmm0
0x180010a75  mov     rax, [rax+80h]
0x180010a7c  jmp     loc_18001090E
0x180010a81  mov     rcx, [rbx+18h]
0x180010a85  mov     rax, [rcx]
0x180010a88  mov     rax, [rax+78h]
0x180010a8c  jmp     loc_18001090A
0x180010a91  mov     rdx, [rbx+38h]
0x180010a95  mov     rcx, [rbx+18h]
0x180010a99  mov     r9, [rbx+30h]
0x180010a9d  mov     r8, [rbx+28h]
0x180010aa1  mov     [rsp+48h+ppv], rdx
0x180010aa6  mov     rax, [rcx]
0x180010aa9  mov     edx, [rbx+20h]
0x180010aac  mov     rax, [rax+18h]
0x180010ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab5  jmp     loc_180010B3B
0x180010aba  sub     edx, 15h
0x180010abd  jz      short loc_180010B1D
0x180010abf  sub     edx, 1
0x180010ac2  jz      short loc_180010B06
0x180010ac4  sub     edx, 1
0x180010ac7  jz      short loc_180010B06
0x180010ac9  sub     edx, 1
0x180010acc  jz      short loc_180010AEB
0x180010ace  cmp     edx, 1
0x180010ad1  jz      short loc_180010ADB
0x180010ad3  mov     dword ptr [rbx], 80004001h
0x180010ad9  jmp     short loc_180010B3D
0x180010adb  mov     rcx, [rbx+18h]
0x180010adf  mov     rax, [rcx]
0x180010ae2  mov     rax, [rax+28h]
0x180010ae6  jmp     loc_180010A1F
0x180010aeb  mov     rcx, [rbx+18h]
0x180010aef  test    rcx, rcx
0x180010af2  jz      short loc_180010B3D
0x180010af4  mov     rax, [rcx]
0x180010af7  mov     rdx, [rbx+20h]
0x180010afb  mov     rax, [rax+20h]
0x180010aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b04  jmp     short loc_180010B3D
0x180010b06  mov     rcx, [rbx+18h]
0x180010b0a  test    rcx, rcx
0x180010b0d  jz      short loc_180010B3D
0x180010b0f  mov     rax, [rcx]
0x180010b12  mov     rax, [rax+10h]
0x180010b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1b  jmp     short loc_180010B3D
0x180010b1d  lea     rcx, [rbx+20h]; rclsid
0x180010b21  xor     r8d, r8d; pvReserved
0x180010b24  mov     rax, [rcx+20h]
0x180010b28  lea     r9, [rcx+10h]; riid
0x180010b2c  mov     [rsp+48h+ppv], rax; ppv
0x180010b31  lea     edx, [r8+4]; dwClsContext
0x180010b35  call    cs:__imp_CoGetClassObject
0x180010b3b  mov     [rbx], eax
0x180010b3d  test    edi, edi
0x180010b3f  js      short loc_180010B49
0x180010b41  xor     ecx, ecx; pReserved
0x180010b43  call    cs:__imp_CoDisableCallCancellation
0x180010b49  mov     rbx, [rsp+48h+arg_0]
0x180010b4e  xor     eax, eax
0x180010b50  add     rsp, 40h
0x180010b54  pop     rdi
0x180010b55  retn
```
