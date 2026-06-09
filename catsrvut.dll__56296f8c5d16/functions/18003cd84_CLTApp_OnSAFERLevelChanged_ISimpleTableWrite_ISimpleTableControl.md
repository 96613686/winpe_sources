# CLTApp::OnSAFERLevelChanged(ISimpleTableWrite *,ISimpleTableControl *)

- ea: `0x18003cd84`
- end: `0x18003d09d`
- name: `?OnSAFERLevelChanged@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(CLTApp *__hidden this, struct ISimpleTableWrite *, struct ISimpleTableControl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x18003b36c`
- `0x18003cd84`
- `0x180054f78`
- `0x180055258`
- `0x180057010`

## import_xrefs

- `ADVAPI32!SaferCloseLevel` at `0x18003cebe`
- `ADVAPI32!SaferCloseLevel` at `0x18003cebe`
- `ADVAPI32!SaferCreateLevel` at `0x18003cea6`
- `ADVAPI32!SaferCreateLevel` at `0x18003cea6`
- `CLBCatQ!ServerGetApplicationType` at `0x18003cf6d`
- `CLBCatQ!ServerGetApplicationType` at `0x18003cf6d`

## pseudocode

```c
__int64 __fastcall CLTApp::OnSAFERLevelChanged(
        CLTApp *this,
        struct ISimpleTableWrite *a2,
        struct ISimpleTableControl *a3)
{
  char *v3; // rdi
  __int64 v4; // rax
  __int64 (__fastcall *v6)(char *, __int64, struct ISimpleTableWrite **, _QWORD, _QWORD, _DWORD **); // rax
  int ApplicationType; // ebx
  char v8; // al
  BOOL v9; // esi
  BOOL v10; // edi
  int Dispenser; // eax
  struct ISimpleTableDispenser *v12; // r14
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  _DWORD *v18; // [rsp+58h] [rbp-31h] BYREF
  DWORD *v19; // [rsp+60h] [rbp-29h]
  __int64 v20; // [rsp+68h] [rbp-21h] BYREF
  struct ISimpleTableDispenser *v21; // [rsp+70h] [rbp-19h] BYREF
  SAFER_LEVEL_HANDLE *p_pLevelHandle; // [rsp+78h] [rbp-11h] BYREF
  int v23; // [rsp+80h] [rbp-9h]
  int v24; // [rsp+84h] [rbp-5h]
  int v25; // [rsp+88h] [rbp-1h]
  int v26; // [rsp+8Ch] [rbp+3h]
  __int64 v27; // [rsp+90h] [rbp+7h]
  int v28; // [rsp+98h] [rbp+Fh]
  int v29; // [rsp+9Ch] [rbp+13h]
  int v30; // [rsp+A0h] [rbp+17h]
  int v31; // [rsp+A4h] [rbp+1Bh]
  int v32; // [rsp+F0h] [rbp+67h] BYREF
  struct ISimpleTableWrite *v33; // [rsp+F8h] [rbp+6Fh] BYREF
  struct ISimpleTableControl *v34; // [rsp+100h] [rbp+77h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+108h] [rbp+7Fh] BYREF

  v34 = a3;
  v33 = a2;
  v3 = (char *)this + 8;
  v4 = *((_QWORD *)this + 1);
  v19 = 0;
  v18 = 0;
  v6 = *(__int64 (__fastcall **)(char *, __int64, struct ISimpleTableWrite **, _QWORD, _QWORD, _DWORD **))(v4 + 152);
  LODWORD(v34) = 0;
  LODWORD(v33) = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v32 = 0;
  ApplicationType = v6((char *)this + 8, 52, &v33, 0, 0, &v18);
  if ( ApplicationType >= 0 )
  {
    if ( !v18 )
    {
LABEL_3:
      ApplicationType = -2147418113;
      goto LABEL_34;
    }
    ApplicationType = (*(__int64 (__fastcall **)(char *, __int64, struct ISimpleTableControl **))(*(_QWORD *)v3 + 152LL))(
                        v3,
                        51,
                        &v34);
    if ( ApplicationType >= 0 )
    {
      if ( !v19 )
        goto LABEL_3;
      ApplicationType = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v3 + 152LL))(
                          v3,
                          0,
                          0,
                          0,
                          0,
                          &v20);
      if ( ApplicationType >= 0 )
      {
        v8 = (char)v34;
        if ( ((unsigned __int8)v34 & 2) != 0 )
        {
          pLevelHandle = 0;
          if ( !SaferCreateLevel(1u, *v19, 1u, &pLevelHandle, 0) )
          {
            ApplicationType = -2146367454;
            goto LABEL_34;
          }
          SaferCloseLevel(pLevelHandle);
          v8 = (char)v34;
        }
        if ( ((unsigned __int8)v33 & 2) != 0 )
        {
          v9 = *v18 == 0;
          v10 = *v18 != 0;
        }
        else
        {
          if ( (v8 & 2) == 0 || !*v18 )
            goto LABEL_34;
          v9 = 0;
          v10 = 1;
        }
        LODWORD(pLevelHandle) = 1;
        p_pLevelHandle = &pLevelHandle;
        v27 = v20;
        v23 = 0;
        v24 = -268435451;
        v25 = 19;
        v26 = 4;
        v28 = 0;
        v29 = 9;
        v30 = 72;
        v31 = 16;
        Dispenser = CLTApp::GetDispenser(this, &v21);
        v12 = v21;
        ApplicationType = Dispenser;
        if ( Dispenser >= 0 )
        {
          ApplicationType = ServerGetApplicationType(v21, v20, &v32);
          if ( ApplicationType >= 0 )
          {
            v13 = 0x400000;
            if ( v32 == 1 )
              v13 = 0x200000;
            ApplicationType = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, SAFER_LEVEL_HANDLE **, __int64, int, int, __int64 *))(*(_QWORD *)v12 + 24LL))(
                                v12,
                                &didCOMSERVICES,
                                &tidCOMSERVICES_CLASSES,
                                &p_pLevelHandle,
                                2,
                                1,
                                v13,
                                &v17);
            if ( ApplicationType >= 0 )
            {
              ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
              if ( ApplicationType >= 0 )
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    v21 = 0;
                    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
                    ApplicationType = v14;
                    if ( v14 == -2146367487 )
                    {
                      ApplicationType = 0;
                      goto LABEL_32;
                    }
                    if ( v14 < 0 )
                      goto LABEL_32;
                    ApplicationType = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, struct ISimpleTableDispenser **))(*(_QWORD *)v17 + 64LL))(
                                        v17,
                                        1,
                                        0,
                                        0,
                                        &v21);
                    if ( ApplicationType < 0 )
                      goto LABEL_32;
                    if ( !v10 )
                      break;
                    v15 = SetFileSAFERLevel((const unsigned __int16 *)v21, *v19);
LABEL_29:
                    ApplicationType = v15;
                    if ( v15 < 0 )
                      goto LABEL_32;
                  }
                  if ( v9 )
                  {
                    v15 = DisableSAFERForFile((const unsigned __int16 *)v21);
                    goto LABEL_29;
                  }
                }
              }
            }
          }
        }
LABEL_32:
        if ( v12 )
          (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
  }
LABEL_34:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)ApplicationType;
}

```

## disassembly

```asm
0x18003cd84  mov     [rsp-8+arg_10], r8
0x18003cd89  mov     [rsp-8+arg_8], rdx
0x18003cd8e  push    rbp
0x18003cd8f  push    rbx
0x18003cd90  push    rsi
0x18003cd91  push    rdi
0x18003cd92  push    r12
0x18003cd94  push    r14
0x18003cd96  push    r15
0x18003cd98  lea     rbp, [rsp-27h]
0x18003cd9d  sub     rsp, 0B0h
0x18003cda4  xor     r15d, r15d
0x18003cda7  lea     rdi, [rcx+8]
0x18003cdab  mov     rax, [rdi]
0x18003cdae  lea     r8, [rbp+57h+arg_8]
0x18003cdb2  mov     r14, rcx
0x18003cdb5  mov     [rbp+57h+var_80], r15
0x18003cdb9  lea     rcx, [rbp+57h+var_88]
0x18003cdbd  mov     [rbp+57h+var_88], r15
0x18003cdc1  mov     [rsp+0E0h+var_B8], rcx
0x18003cdc6  lea     edx, [r15+34h]
0x18003cdca  mov     rax, [rax+98h]
0x18003cdd1  xor     r9d, r9d
0x18003cdd4  mov     rcx, rdi
0x18003cdd7  mov     dword ptr [rbp+57h+arg_10], r15d
0x18003cddb  mov     dword ptr [rbp+57h+arg_8], r15d
0x18003cddf  mov     [rbp+57h+var_78], r15
0x18003cde3  mov     [rbp+57h+var_70], r15
0x18003cde7  mov     [rbp+57h+var_90], r15
0x18003cdeb  mov     [rbp+57h+arg_0], r15d
0x18003cdef  mov     [rsp+0E0h+lpReserved], r15
0x18003cdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdf9  mov     ebx, eax
0x18003cdfb  test    eax, eax
0x18003cdfd  js      loc_18003D074
0x18003ce03  cmp     [rbp+57h+var_88], r15
0x18003ce07  jnz     short loc_18003CE13
0x18003ce09  mov     ebx, 8000FFFFh
0x18003ce0e  jmp     loc_18003D074
0x18003ce13  mov     rax, [rdi]
0x18003ce16  lea     rcx, [rbp+57h+var_80]
0x18003ce1a  mov     [rsp+0E0h+var_B8], rcx
0x18003ce1f  lea     r8, [rbp+57h+arg_10]
0x18003ce23  xor     r9d, r9d
0x18003ce26  mov     [rsp+0E0h+lpReserved], r15
0x18003ce2b  mov     rcx, rdi
0x18003ce2e  mov     rax, [rax+98h]
0x18003ce35  lea     edx, [r9+33h]
0x18003ce39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce3e  mov     ebx, eax
0x18003ce40  test    eax, eax
0x18003ce42  js      loc_18003D074
0x18003ce48  cmp     [rbp+57h+var_80], r15
0x18003ce4c  jz      short loc_18003CE09
0x18003ce4e  mov     rax, [rdi]
0x18003ce51  lea     rcx, [rbp+57h+var_78]
0x18003ce55  mov     [rsp+0E0h+var_B8], rcx
0x18003ce5a  xor     r9d, r9d
0x18003ce5d  xor     r8d, r8d
0x18003ce60  mov     [rsp+0E0h+lpReserved], r15
0x18003ce65  xor     edx, edx
0x18003ce67  mov     rcx, rdi
0x18003ce6a  mov     rax, [rax+98h]
0x18003ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce76  mov     ebx, eax
0x18003ce78  test    eax, eax
0x18003ce7a  js      loc_18003D074
0x18003ce80  mov     eax, dword ptr [rbp+57h+arg_10]
0x18003ce83  mov     r12d, 1
0x18003ce89  test    al, 2
0x18003ce8b  jz      short loc_18003CEC7
0x18003ce8d  mov     rdx, [rbp+57h+var_80]
0x18003ce91  lea     r9, [rbp+57h+pLevelHandle]; pLevelHandle
0x18003ce95  mov     r8d, r12d; OpenFlags
0x18003ce98  mov     [rbp+57h+pLevelHandle], r15
0x18003ce9c  mov     ecx, r12d; dwScopeId
0x18003ce9f  mov     [rsp+0E0h+lpReserved], r15; lpReserved
0x18003cea4  mov     edx, [rdx]; dwLevelId
0x18003cea6  call    cs:__imp_SaferCreateLevel
0x18003ceac  test    eax, eax
0x18003ceae  jnz     short loc_18003CEBA
0x18003ceb0  mov     ebx, 80110822h
0x18003ceb5  jmp     loc_18003D074
0x18003ceba  mov     rcx, [rbp+57h+pLevelHandle]; hLevelHandle
0x18003cebe  call    cs:__imp_SaferCloseLevel
0x18003cec4  mov     eax, dword ptr [rbp+57h+arg_10]
0x18003cec7  test    byte ptr [rbp+57h+arg_8], 2
0x18003cecb  jz      short loc_18003CEE7
0x18003cecd  mov     rax, [rbp+57h+var_88]
0x18003ced1  mov     esi, r15d
0x18003ced4  mov     edi, r15d
0x18003ced7  mov     ecx, [rax]
0x18003ced9  test    ecx, ecx
0x18003cedb  setz    sil
0x18003cedf  test    ecx, ecx
0x18003cee1  setnz   dil
0x18003cee5  jmp     short loc_18003CF02
0x18003cee7  test    al, 2
0x18003cee9  jz      loc_18003D074
0x18003ceef  mov     rax, [rbp+57h+var_88]
0x18003cef3  cmp     [rax], r15d
0x18003cef6  jz      loc_18003D074
0x18003cefc  mov     esi, r15d
0x18003ceff  mov     edi, r12d
0x18003cf02  lea     rax, [rbp+57h+pLevelHandle]
0x18003cf06  mov     dword ptr [rbp+57h+pLevelHandle], r12d
0x18003cf0a  mov     [rbp+57h+var_68], rax
0x18003cf0e  lea     rdx, [rbp+57h+var_70]; struct ISimpleTableDispenser **
0x18003cf12  mov     rax, [rbp+57h+var_78]
0x18003cf16  mov     rcx, r14; this
0x18003cf19  mov     [rbp+57h+var_50], rax
0x18003cf1d  mov     [rbp+57h+var_60], r15d
0x18003cf21  mov     [rbp+57h+var_5C], 0F0000005h
0x18003cf28  mov     [rbp+57h+var_58], 13h
0x18003cf2f  mov     [rbp+57h+var_54], 4
0x18003cf36  mov     [rbp+57h+var_48], r15d
0x18003cf3a  mov     [rbp+57h+var_44], 9
0x18003cf41  mov     [rbp+57h+var_40], 48h ; 'H'
0x18003cf48  mov     [rbp+57h+var_3C], 10h
0x18003cf4f  call    ?GetDispenser@CLTApp@@AEAAJPEAPEAUISimpleTableDispenser@@@Z; CLTApp::GetDispenser(ISimpleTableDispenser * *)
0x18003cf54  mov     r14, [rbp+57h+var_70]
0x18003cf58  mov     ebx, eax
0x18003cf5a  test    eax, eax
0x18003cf5c  js      loc_18003D060
0x18003cf62  mov     rdx, [rbp+57h+var_78]
0x18003cf66  lea     r8, [rbp+57h+arg_0]
0x18003cf6a  mov     rcx, r14
0x18003cf6d  call    cs:__imp_ServerGetApplicationType
0x18003cf73  mov     ebx, eax
0x18003cf75  test    eax, eax
0x18003cf77  js      loc_18003D060
0x18003cf7d  cmp     [rbp+57h+arg_0], r12d
0x18003cf81  lea     rdx, [rbp+57h+var_90]
0x18003cf85  mov     [rsp+0E0h+var_A8], rdx
0x18003cf8a  lea     r9, [rbp+57h+var_68]
0x18003cf8e  mov     ecx, 400000h
0x18003cf93  lea     r8, tidCOMSERVICES_CLASSES
0x18003cf9a  mov     eax, 200000h
0x18003cf9f  lea     rdx, didCOMSERVICES
0x18003cfa6  cmovz   ecx, eax
0x18003cfa9  mov     rax, [r14]
0x18003cfac  mov     [rsp+0E0h+var_B0], ecx
0x18003cfb0  mov     rcx, r14
0x18003cfb3  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x18003cfb8  mov     [rsp+0E0h+lpReserved], 2
0x18003cfc1  mov     rax, [rax+18h]
0x18003cfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfca  mov     ebx, eax
0x18003cfcc  test    eax, eax
0x18003cfce  js      loc_18003D060
0x18003cfd4  mov     rcx, [rbp+57h+var_90]
0x18003cfd8  mov     rax, [rcx]
0x18003cfdb  mov     rax, [rax+18h]
0x18003cfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfe4  mov     ebx, eax
0x18003cfe6  test    eax, eax
0x18003cfe8  js      short loc_18003D060
0x18003cfea  mov     rcx, [rbp+57h+var_90]
0x18003cfee  mov     [rbp+57h+var_70], r15
0x18003cff2  mov     rax, [rcx]
0x18003cff5  mov     rax, [rax+28h]
0x18003cff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cffe  mov     ebx, eax
0x18003d000  cmp     eax, 80110801h
0x18003d005  jz      short loc_18003D05D
0x18003d007  test    eax, eax
0x18003d009  js      short loc_18003D060
0x18003d00b  mov     rcx, [rbp+57h+var_90]
0x18003d00f  lea     rdx, [rbp+57h+var_70]
0x18003d013  mov     [rsp+0E0h+lpReserved], rdx
0x18003d018  xor     r9d, r9d
0x18003d01b  xor     r8d, r8d
0x18003d01e  mov     edx, r12d
0x18003d021  mov     rax, [rcx]
0x18003d024  mov     rax, [rax+40h]
0x18003d028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d02d  mov     ebx, eax
0x18003d02f  test    eax, eax
0x18003d031  js      short loc_18003D060
0x18003d033  test    edi, edi
0x18003d035  jz      short loc_18003D048
0x18003d037  mov     rdx, [rbp+57h+var_80]
0x18003d03b  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18003d03f  mov     edx, [rdx]; dwLevelId
0x18003d041  call    ?SetFileSAFERLevel@@YAJPEBGK@Z; SetFileSAFERLevel(ushort const *,ulong)
0x18003d046  jmp     short loc_18003D055
0x18003d048  test    esi, esi
0x18003d04a  jz      short loc_18003CFEA
0x18003d04c  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18003d050  call    ?DisableSAFERForFile@@YAJPEBG@Z; DisableSAFERForFile(ushort const *)
0x18003d055  mov     ebx, eax
0x18003d057  test    eax, eax
0x18003d059  jns     short loc_18003CFEA
0x18003d05b  jmp     short loc_18003D060
0x18003d05d  mov     ebx, r15d
0x18003d060  test    r14, r14
0x18003d063  jz      short loc_18003D074
0x18003d065  mov     rax, [r14]
0x18003d068  mov     rcx, r14
0x18003d06b  mov     rax, [rax+10h]
0x18003d06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d074  mov     rcx, [rbp+57h+var_90]
0x18003d078  test    rcx, rcx
0x18003d07b  jz      short loc_18003D089
0x18003d07d  mov     rax, [rcx]
0x18003d080  mov     rax, [rax+10h]
0x18003d084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d089  mov     eax, ebx
0x18003d08b  add     rsp, 0B0h
0x18003d092  pop     r15
0x18003d094  pop     r14
0x18003d096  pop     r12
0x18003d098  pop     rdi
0x18003d099  pop     rsi
0x18003d09a  pop     rbx
0x18003d09b  pop     rbp
0x18003d09c  retn
```
