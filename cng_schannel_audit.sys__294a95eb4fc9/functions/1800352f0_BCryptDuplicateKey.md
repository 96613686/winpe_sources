# BCryptDuplicateKey

- ea: `0x1800352f0`
- end: `0x180035533`
- name: `BCryptDuplicateKey`
- size: `579`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, BCRYPT_KEY_HANDLE *phNewKey, PUCHAR pbKeyObject, ULONG cbKeyObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003b10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x1800352f0`
- `0x1800358a0`
- `0x18005bad0`
- `0x18009d860`

## string_xrefs

- `0x180035412`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180035476`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800354c2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800354e9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDuplicateKey(
        BCRYPT_KEY_HANDLE hKey,
        BCRYPT_KEY_HANDLE *phNewKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        ULONG dwFlags)
{
  void *v5; // rdi
  ULONG v6; // ebp
  PUCHAR v7; // rbx
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // r13
  __int64 v13; // rsi
  _DWORD *v14; // r14
  int v15; // eax
  NTSTATUS v16; // ebx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  ULONG v21; // [rsp+40h] [rbp-58h] BYREF
  void *v22; // [rsp+48h] [rbp-50h] BYREF

  v5 = 0;
  v6 = cbKeyObject;
  v22 = 0;
  v7 = pbKeyObject;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      30,
      pbKeyObject,
      hKey,
      phNewKey,
      pbKeyObject,
      cbKeyObject,
      dwFlags);
  v10 = ValidateBaseKeyHandle(hKey);
  v12 = v10;
  if ( v10 )
  {
    if ( !phNewKey )
    {
      v16 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5460);
      return v16;
    }
    v13 = *(_QWORD *)(v10 + 8);
    if ( !v7 )
    {
      if ( !v6 )
      {
        v18 = AllocateObjectBuffer(*(_QWORD *)(v10 + 8), &v22, &v21);
        v16 = v18;
        if ( v18 < 0 )
        {
          DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5475);
          v5 = v22;
          goto LABEL_9;
        }
        v5 = v22;
        v6 = v21;
        v7 = (PUCHAR)v22;
      }
      if ( !v7 )
      {
        v16 = -1073741811;
        v19 = 5492;
        v20 = 3221225485LL;
        goto LABEL_25;
      }
    }
    if ( v6 < 0x3E )
    {
      v16 = -1073741789;
      goto LABEL_9;
    }
    v14 = (_DWORD *)((unsigned __int64)(v7 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
    *v14 = 32;
    v14[1] = 1431655762;
    *((_QWORD *)v14 + 1) = v13;
    *((_QWORD *)v14 + 3) = v5;
    if ( *(_DWORD *)(v13 + 36) != 1 && *(_DWORD *)(v13 + 36) != 7 )
    {
      v16 = -1073741637;
      v19 = 5528;
      v20 = 3221225659LL;
      goto LABEL_25;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, ULONG))(v13 + 128))(
            *(_QWORD *)(v12 + 16),
            v14 + 4,
            ((unsigned __int64)v14 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
            (_DWORD)v7 - (((_DWORD)v14 + 47) & 0xFFFFFFF0) + v6,
            dwFlags);
    v16 = v15;
    if ( v15 < 0 )
    {
      v19 = 5539;
      v20 = (unsigned int)v15;
LABEL_25:
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v19);
      goto LABEL_9;
    }
    v5 = 0;
    *phNewKey = v14;
LABEL_9:
    if ( v5 )
      MSCryptFree(v5);
    if ( v13 && v16 >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
    return v16;
  }
  v16 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      77);
  return v16;
}

```

## disassembly

```asm
0x1800352f0  push    rbx
0x1800352f2  push    rbp
0x1800352f3  push    rsi
0x1800352f4  push    rdi
0x1800352f5  push    r12
0x1800352f7  push    r13
0x1800352f9  push    r14
0x1800352fb  push    r15
0x1800352fd  sub     rsp, 58h
0x180035301  xor     edi, edi
0x180035303  mov     ebp, r9d
0x180035306  mov     [rsp+98h+var_50], rdi
0x18003530b  mov     rbx, r8
0x18003530e  mov     [rsp+98h+var_58], edi
0x180035312  mov     r15, rdx
0x180035315  mov     rsi, rcx
0x180035318  mov     rcx, cs:WPP_GLOBAL_Control
0x18003531f  lea     r14, WPP_GLOBAL_Control
0x180035326  mov     r12d, [rsp+98h+dwFlags]
0x18003532e  cmp     rcx, r14
0x180035331  jnz     loc_18003543C
0x180035337  mov     rcx, rsi
0x18003533a  call    ValidateBaseKeyHandle
0x18003533f  mov     r13, rax
0x180035342  test    rax, rax
0x180035345  jz      loc_1800353F6
0x18003534b  test    r15, r15
0x18003534e  jz      loc_180035470
0x180035354  mov     rsi, [rax+8]
0x180035358  test    rbx, rbx
0x18003535b  jz      loc_180035498
0x180035361  cmp     ebp, 3Eh ; '>'
0x180035364  jb      loc_180035501
0x18003536a  lea     r14, [rbx+0Fh]
0x18003536e  and     r14, 0FFFFFFFFFFFFFFF0h
0x180035372  mov     dword ptr [r14], 20h ; ' '
0x180035379  mov     dword ptr [r14+4], 55555552h
0x180035381  mov     [r14+8], rsi
0x180035385  mov     [r14+18h], rdi
0x180035389  mov     ecx, [rsi+24h]
0x18003538c  sub     ecx, 1
0x18003538f  jnz     loc_18003550B
0x180035395  mov     rax, [rsi+80h]
0x18003539c  lea     r8, [r14+2Fh]
0x1800353a0  mov     rcx, [r13+10h]
0x1800353a4  lea     rdx, [r14+10h]
0x1800353a8  and     r8, 0FFFFFFFFFFFFFFF0h
0x1800353ac  mov     dword ptr [rsp+98h+var_78], r12d
0x1800353b1  sub     ebx, r8d
0x1800353b4  lea     r9d, [rbx+rbp]
0x1800353b8  call    _guard_dispatch_icall
0x1800353bd  mov     ebx, eax
0x1800353bf  test    eax, eax
0x1800353c1  js      loc_1800354E1
0x1800353c7  xor     edi, edi
0x1800353c9  mov     [r15], r14
0x1800353cc  test    rdi, rdi
0x1800353cf  jnz     loc_180035526
0x1800353d5  test    rsi, rsi
0x1800353d8  jz      short loc_1800353E2
0x1800353da  test    ebx, ebx
0x1800353dc  js      short loc_1800353E2
0x1800353de  lock inc dword ptr [rsi+10h]
0x1800353e2  mov     eax, ebx
0x1800353e4  add     rsp, 58h
0x1800353e8  pop     r15
0x1800353ea  pop     r14
0x1800353ec  pop     r13
0x1800353ee  pop     r12
0x1800353f0  pop     rdi
0x1800353f1  pop     rsi
0x1800353f2  pop     rbp
0x1800353f3  pop     rbx
0x1800353f4  retn
0x1800353f6  mov     ebx, 0C0000008h
0x1800353fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035402  cmp     rcx, r14
0x180035405  jz      short loc_1800353E2
0x180035407  mov     eax, [rcx+2Ch]
0x18003540a  test    al, 1
0x18003540c  jz      short loc_1800353E2
0x18003540e  mov     rcx, [rcx+18h]
0x180035412  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035419  mov     [rsp+98h+var_68], 154Dh
0x180035421  lea     r9, aStatus; "Status"
0x180035428  mov     [rsp+98h+var_70], r8
0x18003542d  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x180035435  call    WPP_SF_sDsd
0x18003543a  jmp     short loc_1800353E2
0x18003543c  mov     eax, [rcx+2Ch]
0x18003543f  test    al, 4
0x180035441  jz      loc_180035337
0x180035447  mov     rcx, [rcx+18h]
0x18003544b  mov     edx, 1Eh
0x180035450  mov     [rsp+98h+var_60], r12d
0x180035455  mov     r9, rsi
0x180035458  mov     [rsp+98h+var_68], ebp
0x18003545c  mov     [rsp+98h+var_70], rbx
0x180035461  mov     [rsp+98h+var_78], r15
0x180035466  call    WPP_SF_qqqdD
0x18003546b  jmp     loc_180035337
0x180035470  mov     r9d, 1554h
0x180035476  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003547d  lea     rdx, aStatus; "Status"
0x180035484  mov     ecx, 0C000000Dh
0x180035489  mov     ebx, 0C000000Dh
0x18003548e  call    DebugTraceError
0x180035493  jmp     loc_1800353E2
0x180035498  test    ebp, ebp
0x18003549a  jnz     loc_1800A0DFC
0x1800354a0  lea     r8, [rsp+98h+var_58]
0x1800354a5  mov     rcx, rsi
0x1800354a8  lea     rdx, [rsp+98h+var_50]
0x1800354ad  call    AllocateObjectBuffer
0x1800354b2  mov     ebx, eax
0x1800354b4  test    eax, eax
0x1800354b6  jns     loc_1800A0DF0
0x1800354bc  mov     r9d, 1563h
0x1800354c2  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800354c9  lea     rdx, aStatus; "Status"
0x1800354d0  mov     ecx, eax
0x1800354d2  call    DebugTraceError
0x1800354d7  mov     rdi, [rsp+98h+var_50]
0x1800354dc  jmp     loc_1800353CC
0x1800354e1  mov     r9d, 15A3h
0x1800354e7  mov     ecx, eax
0x1800354e9  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800354f0  lea     rdx, aStatus; "Status"
0x1800354f7  call    DebugTraceError
0x1800354fc  jmp     loc_1800353CC
0x180035501  mov     ebx, 0C0000023h
0x180035506  jmp     loc_1800353CC
0x18003550b  cmp     ecx, 6
0x18003550e  jz      loc_180035395
0x180035514  mov     ebx, 0C00000BBh
0x180035519  mov     r9d, 1598h
0x18003551f  mov     ecx, 0C00000BBh
0x180035524  jmp     short loc_1800354E9
0x180035526  mov     rcx, rdi; P
0x180035529  call    MSCryptFree
0x18003552e  jmp     loc_1800353D5
0x1800a0df0  mov     rdi, [rsp+98h+var_50]
0x1800a0df5  mov     ebp, [rsp+98h+var_58]
0x1800a0df9  mov     rbx, rdi
0x1800a0dfc  test    rbx, rbx
0x1800a0dff  jnz     loc_180035361
0x1800a0e05  mov     ebx, 0C000000Dh
0x1800a0e0a  mov     r9d, 1574h
0x1800a0e10  mov     ecx, 0C000000Dh
0x1800a0e15  jmp     loc_1800354E9
```
