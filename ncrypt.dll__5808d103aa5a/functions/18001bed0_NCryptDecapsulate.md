# NCryptDecapsulate

- ea: `0x18001bed0`
- end: `0x18001c09c`
- name: `NCryptDecapsulate`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x18001bed0`
- `0x180020010`

## string_xrefs

- `0x18001c02a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001c072`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __fastcall NCryptDecapsulate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  unsigned int v8; // r13d
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rdi
  __int64 v16; // rax
  unsigned int v17; // eax
  NCRYPT_KEY_HANDLE *v18; // rdx
  NCryptKeyName **v19; // r8
  NCryptAlgorithmName **v20; // r9
  int v21; // r9d

  v8 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, a3, a1);
  if ( !a6 )
  {
    v10 = -2146893785;
    v11 = 4772;
    v12 = 2148073511LL;
LABEL_19:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v11);
    return NormalizeNteStatus(v10, v18, v19, v20, a5, a6, a7);
  }
  v13 = ValidateClientKeyHandle(a1);
  v15 = (_QWORD *)v13;
  if ( !v13 )
  {
    v10 = -2146893786;
    v11 = 4781;
    v12 = 2148073510LL;
    goto LABEL_19;
  }
  v16 = *(_QWORD *)(v13 + 8);
  if ( *(_WORD *)(v16 + 16) < 4u || !*(_QWORD *)(v16 + 264) )
  {
    v10 = -2146893783;
    v11 = 4793;
    v12 = 2148073513LL;
    goto LABEL_19;
  }
  while ( 1 )
  {
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, _DWORD, DWORD *, _DWORD))(v15[1] + 264LL))(
            *(_QWORD *)(v15[1] + 272LL),
            v15[2],
            v14,
            v8,
            a4,
            (_DWORD)a5,
            a6,
            (_DWORD)a7);
    v10 = v17;
    if ( v17 != -2146893778 )
      break;
    if ( ((unsigned __int8)a7 & 0x40) != 0 )
    {
      v10 = -2146893790;
      v11 = 4818;
      v12 = 2148073506LL;
      goto LABEL_19;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD))(v15[1] + 192LL))(
            *(_QWORD *)(v15[1] + 272LL),
            a1,
            L"NCryptDecapsulate",
            0);
    if ( v10 )
      goto LABEL_16;
    v14 = a2;
  }
  if ( v17 )
  {
LABEL_16:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4836);
    EtwLogNCryptOperationFailed(19, *(_QWORD *)(v15[1] + 280LL), v15[3], v21, v10);
    return NormalizeNteStatus(v10, v18, v19, v20, a5, a6, a7);
  }
  v10 = 0;
  return NormalizeNteStatus(v10, v18, v19, v20, a5, a6, a7);
}

```

## disassembly

```asm
0x18001bed0  mov     [rsp+arg_8], rdx
0x18001bed5  push    rbx
0x18001bed6  push    rbp
0x18001bed7  push    rsi
0x18001bed8  push    rdi
0x18001bed9  push    r12
0x18001bedb  push    r13
0x18001bedd  push    r14
0x18001bedf  push    r15
0x18001bee1  sub     rsp, 58h
0x18001bee5  mov     r12, r9
0x18001bee8  mov     r13d, r8d
0x18001beeb  mov     rsi, rcx
0x18001beee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bef5  lea     rax, WPP_GLOBAL_Control
0x18001befc  mov     ebp, [rsp+98h+arg_30]
0x18001bf03  cmp     rcx, rax
0x18001bf06  jz      short loc_18001BF2B
0x18001bf08  test    byte ptr [rcx+1Ch], 4
0x18001bf0c  jz      short loc_18001BF2B
0x18001bf0e  mov     rcx, [rcx+10h]
0x18001bf12  mov     edx, 27h ; '''
0x18001bf17  mov     r9, rsi
0x18001bf1a  mov     dword ptr [rsp+98h+var_78], ebp
0x18001bf1e  call    WPP_SF_PD
0x18001bf23  mov     rdx, [rsp+98h+arg_8]
0x18001bf2b  mov     r14, [rsp+98h+arg_28]
0x18001bf33  test    r14, r14
0x18001bf36  jnz     short loc_18001BF4D
0x18001bf38  mov     ebx, 80090027h
0x18001bf3d  mov     r9d, 12A4h
0x18001bf43  mov     ecx, 80090027h
0x18001bf48  jmp     loc_18001C072
0x18001bf4d  mov     rcx, rsi
0x18001bf50  call    ValidateClientKeyHandle
0x18001bf55  mov     rdi, rax
0x18001bf58  test    rax, rax
0x18001bf5b  jnz     short loc_18001BF72
0x18001bf5d  mov     ebx, 80090026h
0x18001bf62  mov     r9d, 12ADh
0x18001bf68  mov     ecx, 80090026h
0x18001bf6d  jmp     loc_18001C072
0x18001bf72  mov     rax, [rax+8]
0x18001bf76  cmp     word ptr [rax+10h], 4
0x18001bf7b  jb      loc_18001C062
0x18001bf81  cmp     qword ptr [rax+108h], 0
0x18001bf89  jz      loc_18001C062
0x18001bf8f  mov     r15d, dword ptr [rsp+98h+arg_20]
0x18001bf97  mov     rcx, [rdi+8]
0x18001bf9b  mov     r8, rdx
0x18001bf9e  mov     rdx, [rdi+10h]
0x18001bfa2  mov     r9d, r13d
0x18001bfa5  mov     [rsp+98h+var_60], ebp
0x18001bfa9  mov     [rsp+98h+var_68], r14
0x18001bfae  mov     rax, [rcx+108h]
0x18001bfb5  mov     rcx, [rcx+110h]
0x18001bfbc  mov     [rsp+98h+var_70], r15d
0x18001bfc1  mov     [rsp+98h+var_78], r12
0x18001bfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfcb  mov     ebx, eax
0x18001bfcd  cmp     eax, 8009002Eh
0x18001bfd2  jnz     short loc_18001C020
0x18001bfd4  test    bpl, 40h
0x18001bfd8  jnz     short loc_18001C00E
0x18001bfda  mov     rcx, [rdi+8]
0x18001bfde  lea     r8, aNcryptdecapsul_0; "NCryptDecapsulate"
0x18001bfe5  xor     r9d, r9d
0x18001bfe8  mov     rdx, rsi
0x18001bfeb  mov     rax, [rcx+0C0h]
0x18001bff2  mov     rcx, [rcx+110h]
0x18001bff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bffe  mov     ebx, eax
0x18001c000  test    eax, eax
0x18001c002  jnz     short loc_18001C024
0x18001c004  mov     rdx, [rsp+98h+arg_8]
0x18001c00c  jmp     short loc_18001BF97
0x18001c00e  mov     ebx, 80090022h
0x18001c013  mov     r9d, 12D2h
0x18001c019  mov     ecx, 80090022h
0x18001c01e  jmp     short loc_18001C072
0x18001c020  test    eax, eax
0x18001c022  jz      short loc_18001C05E
0x18001c024  mov     r9d, 12E4h
0x18001c02a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c031  lea     rdx, aStatus; "Status"
0x18001c038  mov     ecx, ebx
0x18001c03a  call    DebugTraceError
0x18001c03f  mov     rdx, [rdi+8]
0x18001c043  mov     ecx, 13h
0x18001c048  mov     r8, [rdi+18h]
0x18001c04c  mov     dword ptr [rsp+98h+var_78], ebx
0x18001c050  mov     rdx, [rdx+118h]
0x18001c057  call    EtwLogNCryptOperationFailed
0x18001c05c  jmp     short loc_18001C085
0x18001c05e  xor     ebx, ebx
0x18001c060  jmp     short loc_18001C085
0x18001c062  mov     ebx, 80090029h
0x18001c067  mov     r9d, 12B9h
0x18001c06d  mov     ecx, 80090029h
0x18001c072  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c079  lea     rdx, aStatus; "Status"
0x18001c080  call    DebugTraceError
0x18001c085  mov     ecx, ebx
0x18001c087  add     rsp, 58h
0x18001c08b  pop     r15
0x18001c08d  pop     r14
0x18001c08f  pop     r13
0x18001c091  pop     r12
0x18001c093  pop     rdi
0x18001c094  pop     rsi
0x18001c095  pop     rbp
0x18001c096  pop     rbx
0x18001c097  jmp     NormalizeNteStatus
```
