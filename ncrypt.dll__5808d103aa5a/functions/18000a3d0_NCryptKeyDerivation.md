# NCryptKeyDerivation

- ea: `0x18000a3d0`
- end: `0x18000a640`
- name: `NCryptKeyDerivation`
- size: `624`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a3d0`
- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x180020010`

## string_xrefs

- `0x18000a4f1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000a530`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000a567`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000a5d2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000a61e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __fastcall NCryptKeyDerivation(
        __int64 a1,
        __int64 a2,
        NCryptKeyName **a3,
        PVOID *a4,
        __int64 a5,
        int a6)
{
  int v6; // r15d
  PVOID *v10; // r10
  NCRYPT_KEY_HANDLE *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r10
  _QWORD *v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebx

  v6 = (int)a4;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  v11 = (NCRYPT_KEY_HANDLE *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, a3, a1, a6);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v11 = (NCRYPT_KEY_HANDLE *)&WPP_GLOBAL_Control;
  }
  if ( a5 && a3 && v6 )
  {
    v12 = ValidateClientKeyHandle(a1);
    v14 = (_QWORD *)v12;
    if ( v12 )
    {
      v15 = *(_QWORD *)(v12 + 8);
      if ( *(_WORD *)(v15 + 16) >= 2u && *(_QWORD *)(v15 + 232) )
      {
        while ( 1 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, NCryptKeyName **, int, __int64, int))(v14[1] + 232LL))(
                  *(_QWORD *)(v14[1] + 272LL),
                  v14[2],
                  a2,
                  a3,
                  v6,
                  a5,
                  a6);
          v17 = v16;
          if ( v16 != -2146893778 )
            break;
          if ( (a6 & 0x40) != 0 )
          {
            v17 = -2146893790;
            DebugTraceError(
              2148073506LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              4313);
            return NormalizeNteStatus(v17, v11, a3, a4, a5);
          }
          v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD))(v14[1] + 192LL))(
                  *(_QWORD *)(v14[1] + 272LL),
                  a1,
                  L"NCryptKeyDerivation",
                  0);
          if ( v17 )
            goto LABEL_25;
        }
        if ( !v16 )
          return NormalizeNteStatus(v17, v11, a3, a4, a5);
LABEL_25:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v11,
            (_DWORD)a3,
            (unsigned int)"Status",
            v17,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            235);
        EtwLogNCryptOperationFailed(10, *(_QWORD *)(v14[1] + 280LL), v14[3], (_DWORD)a4, v17);
      }
      else
      {
        v17 = -2146893783;
        if ( (NCRYPT_KEY_HANDLE *)v13 != v11 && (*(_BYTE *)(v13 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(v13 + 16),
            (_DWORD)v11,
            (_DWORD)a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            192);
      }
    }
    else
    {
      v17 = -2146893786;
      if ( (NCRYPT_KEY_HANDLE *)v13 != v11 && (*(_BYTE *)(v13 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(v13 + 16),
          (_DWORD)v11,
          (_DWORD)a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          178);
    }
  }
  else
  {
    v17 = -2146893785;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v10[2],
        (unsigned int)&WPP_GLOBAL_Control,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        165);
  }
  return NormalizeNteStatus(v17, v11, a3, a4, a5);
}

```

## disassembly

```asm
0x18000a3d0  push    rbx
0x18000a3d2  push    rbp
0x18000a3d3  push    rsi
0x18000a3d4  push    rdi
0x18000a3d5  push    r12
0x18000a3d7  push    r13
0x18000a3d9  push    r14
0x18000a3db  push    r15
0x18000a3dd  sub     rsp, 48h
0x18000a3e1  mov     r15d, r9d
0x18000a3e4  mov     r12, r8
0x18000a3e7  mov     r13, rdx
0x18000a3ea  mov     rsi, rcx
0x18000a3ed  mov     r10, cs:WPP_GLOBAL_Control
0x18000a3f4  lea     rdx, WPP_GLOBAL_Control
0x18000a3fb  mov     ebp, [rsp+88h+arg_28]
0x18000a402  cmp     r10, rdx
0x18000a405  jz      short loc_18000A431
0x18000a407  test    byte ptr [r10+1Ch], 4
0x18000a40c  jz      short loc_18000A431
0x18000a40e  mov     r9, rcx
0x18000a411  mov     [rsp+88h+var_68], ebp
0x18000a415  mov     rcx, [r10+10h]
0x18000a419  mov     edx, 23h ; '#'
0x18000a41e  call    WPP_SF_PD
0x18000a423  mov     r10, cs:WPP_GLOBAL_Control
0x18000a42a  lea     rdx, WPP_GLOBAL_Control
0x18000a431  mov     r14, [rsp+88h+arg_20]
0x18000a439  test    r14, r14
0x18000a43c  jz      loc_18000A517
0x18000a442  test    r12, r12
0x18000a445  jz      loc_18000A517
0x18000a44b  test    r15d, r15d
0x18000a44e  jz      loc_18000A517
0x18000a454  mov     rcx, rsi
0x18000a457  call    ValidateClientKeyHandle
0x18000a45c  mov     rdi, rax
0x18000a45f  test    rax, rax
0x18000a462  jz      loc_18000A546
0x18000a468  mov     rax, [rax+8]
0x18000a46c  cmp     word ptr [rax+10h], 2
0x18000a471  jb      short loc_18000A4D8
0x18000a473  cmp     qword ptr [rax+0E8h], 0
0x18000a47b  jz      short loc_18000A4D8
0x18000a47d  mov     rcx, [rdi+8]
0x18000a481  mov     r9, r12
0x18000a484  mov     rdx, [rdi+10h]
0x18000a488  mov     r8, r13
0x18000a48b  mov     [rsp+88h+var_58], ebp
0x18000a48f  mov     [rsp+88h+var_60], r14
0x18000a494  mov     rax, [rcx+0E8h]
0x18000a49b  mov     rcx, [rcx+110h]
0x18000a4a2  mov     [rsp+88h+var_68], r15d
0x18000a4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ac  mov     ebx, eax
0x18000a4ae  cmp     eax, 8009002Eh
0x18000a4b3  jz      loc_18000A57D
0x18000a4b9  test    eax, eax
0x18000a4bb  jnz     loc_18000A5B5
0x18000a4c1  mov     ecx, ebx
0x18000a4c3  add     rsp, 48h
0x18000a4c7  pop     r15
0x18000a4c9  pop     r14
0x18000a4cb  pop     r13
0x18000a4cd  pop     r12
0x18000a4cf  pop     rdi
0x18000a4d0  pop     rsi
0x18000a4d1  pop     rbp
0x18000a4d2  pop     rbx
0x18000a4d3  jmp     NormalizeNteStatus
0x18000a4d8  mov     ebx, 80090029h
0x18000a4dd  cmp     r10, rdx
0x18000a4e0  jz      short loc_18000A4C1
0x18000a4e2  test    byte ptr [r10+1Ch], 1
0x18000a4e7  jz      short loc_18000A4C1
0x18000a4e9  mov     [rsp+88h+var_58], 10C0h
0x18000a4f1  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a4f8  mov     [rsp+88h+var_60], rax
0x18000a4fd  mov     [rsp+88h+var_68], 80090029h
0x18000a505  mov     rcx, [r10+10h]
0x18000a509  lea     r9, aStatus; "Status"
0x18000a510  call    WPP_SF_sDsd
0x18000a515  jmp     short loc_18000A4C1
0x18000a517  mov     ebx, 80090027h
0x18000a51c  cmp     r10, rdx
0x18000a51f  jz      short loc_18000A4C1
0x18000a521  test    byte ptr [r10+1Ch], 1
0x18000a526  jz      short loc_18000A4C1
0x18000a528  mov     [rsp+88h+var_58], 10A5h
0x18000a530  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a537  mov     [rsp+88h+var_60], rax
0x18000a53c  mov     [rsp+88h+var_68], 80090027h
0x18000a544  jmp     short loc_18000A505
0x18000a546  mov     ebx, 80090026h
0x18000a54b  cmp     r10, rdx
0x18000a54e  jz      loc_18000A4C1
0x18000a554  test    byte ptr [r10+1Ch], 1
0x18000a559  jz      loc_18000A4C1
0x18000a55f  mov     [rsp+88h+var_58], 10B2h
0x18000a567  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a56e  mov     [rsp+88h+var_60], rax
0x18000a573  mov     [rsp+88h+var_68], 80090026h
0x18000a57b  jmp     short loc_18000A505
0x18000a57d  test    bpl, 40h
0x18000a581  jnz     loc_18000A618
0x18000a587  mov     rcx, [rdi+8]
0x18000a58b  lea     r8, aNcryptkeyderiv_0; "NCryptKeyDerivation"
0x18000a592  xor     r9d, r9d
0x18000a595  mov     rdx, rsi
0x18000a598  mov     rax, [rcx+0C0h]
0x18000a59f  mov     rcx, [rcx+110h]
0x18000a5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ab  mov     ebx, eax
0x18000a5ad  test    eax, eax
0x18000a5af  jz      loc_18000A47D
0x18000a5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5bc  lea     rax, WPP_GLOBAL_Control
0x18000a5c3  cmp     rcx, rax
0x18000a5c6  jz      short loc_18000A5F6
0x18000a5c8  test    byte ptr [rcx+1Ch], 1
0x18000a5cc  jz      short loc_18000A5F6
0x18000a5ce  mov     rcx, [rcx+10h]
0x18000a5d2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a5d9  mov     [rsp+88h+var_58], 10EBh
0x18000a5e1  lea     r9, aStatus; "Status"
0x18000a5e8  mov     [rsp+88h+var_60], rax
0x18000a5ed  mov     [rsp+88h+var_68], ebx
0x18000a5f1  call    WPP_SF_sDsd
0x18000a5f6  mov     rdx, [rdi+8]
0x18000a5fa  mov     ecx, 0Ah
0x18000a5ff  mov     r8, [rdi+18h]
0x18000a603  mov     [rsp+88h+var_68], ebx
0x18000a607  mov     rdx, [rdx+118h]
0x18000a60e  call    EtwLogNCryptOperationFailed
0x18000a613  jmp     loc_18000A4C1
0x18000a618  mov     r9d, 10D9h
0x18000a61e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a625  lea     rdx, aStatus; "Status"
0x18000a62c  mov     ecx, 80090022h
0x18000a631  mov     ebx, 80090022h
0x18000a636  call    DebugTraceError
0x18000a63b  jmp     loc_18000A4C1
```
