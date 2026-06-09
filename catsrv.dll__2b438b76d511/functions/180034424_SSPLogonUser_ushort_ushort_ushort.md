# SSPLogonUser(ushort *,ushort *,ushort *)

- ea: `0x180034424`
- end: `0x1800345c1`
- name: `?SSPLogonUser@@YAHPEAG00@Z`
- size: `413`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800341d0`

## callees

- `0x180009ee0`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x180034424`
- `0x180038494`
- `0x180038628`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800345a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800345a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003447e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003447e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003450c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003450c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800344d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800344d6`
- `SspiCli!LogonUserExExW` at `0x180034476`
- `SspiCli!LogonUserExExW` at `0x180034572`
- `SspiCli!LogonUserExExW` at `0x180034476`
- `SspiCli!LogonUserExExW` at `0x180034572`

## pseudocode

```c
__int64 __fastcall SSPLogonUser(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // esi
  DWORD LastError; // eax
  int v8; // eax
  int v9; // r8d
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  const unsigned __int16 *v14; // rdx
  int v15; // ebp
  const unsigned __int16 *v16; // rdx
  HANDLE hObject; // [rsp+A8h] [rbp+20h] BYREF

  hObject = 0;
  v6 = LogonUserExExW(a2, a1, a3, 3, 0, 0, &hObject, 0, 0, 0, 0);
  LastError = GetLastError();
  if ( v6 )
    goto LABEL_17;
  if ( LastError == 1385 || LastError == 1348 )
  {
    if ( a1 )
      safe_lstrlenW(a1);
    v8 = safe_lstrlenW(a2);
    v10 = (unsigned int)(v9 + v8 + 1);
    v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v11 )
      return 0;
    if ( a1 )
    {
      if ( (int)StringCchPrintfW(v11, v10, L"%s\\", a1) < 0 )
      {
LABEL_10:
        CoTaskMemFree(v12);
        return 0;
      }
    }
    else
    {
      *v11 = 0;
    }
    if ( (int)StringCchCatW(v12, v10, a2) < 0 )
      goto LABEL_10;
    v15 = SetAccountRights(v12, v14);
    if ( v15 < 0 )
      goto LABEL_10;
    v6 = LogonUserExExW(a2, a1, a3, 4, 0, 0, &hObject, 0, 0, 0, 0);
    if ( !v15 )
      RemoveAccountRights(v12, v16);
    CoTaskMemFree(v12);
    if ( v6 )
    {
LABEL_17:
      if ( hObject )
        CloseHandle(hObject);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180034424  mov     r11, rsp
0x180034427  mov     [r11+8], rbx
0x18003442b  mov     [r11+10h], rbp
0x18003442f  push    rsi
0x180034430  push    rdi
0x180034431  push    r12
0x180034433  push    r14
0x180034435  push    r15
0x180034437  sub     rsp, 60h
0x18003443b  xor     r12d, r12d
0x18003443e  lea     rax, [r11+20h]
0x180034442  mov     [r11-38h], r12
0x180034446  mov     r14, rdx
0x180034449  mov     [r11-40h], r12
0x18003444d  mov     rdi, rcx
0x180034450  mov     [r11-48h], r12
0x180034454  mov     rdx, rcx
0x180034457  mov     [r11-50h], r12
0x18003445b  lea     r9d, [r12+3]
0x180034460  mov     [r11-58h], rax
0x180034464  mov     rcx, r14
0x180034467  mov     [r11-60h], r12
0x18003446b  mov     r15, r8
0x18003446e  mov     [r11-68h], r12d
0x180034472  mov     [r11+20h], r12
0x180034476  call    cs:__imp_LogonUserExExW
0x18003447c  mov     esi, eax
0x18003447e  call    cs:__imp_GetLastError
0x180034484  test    esi, esi
0x180034486  jnz     loc_180034593
0x18003448c  cmp     eax, 569h
0x180034491  jz      short loc_18003449E
0x180034493  cmp     eax, 544h
0x180034498  jnz     loc_1800345A6
0x18003449e  mov     r8d, r12d
0x1800344a1  test    rdi, rdi
0x1800344a4  jz      short loc_1800344B2
0x1800344a6  mov     rcx, rdi; unsigned __int16 *
0x1800344a9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800344ae  lea     r8d, [rax+1]
0x1800344b2  mov     rcx, r14; unsigned __int16 *
0x1800344b5  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800344ba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800344c1  lea     esi, [rax+1]
0x1800344c4  mov     eax, 2
0x1800344c9  add     esi, r8d
0x1800344cc  mul     rsi
0x1800344cf  cmovb   rax, rcx
0x1800344d3  mov     rcx, rax; cb
0x1800344d6  call    cs:__imp_CoTaskMemAlloc
0x1800344dc  mov     rbx, rax
0x1800344df  test    rax, rax
0x1800344e2  jnz     short loc_1800344EB
0x1800344e4  xor     eax, eax
0x1800344e6  jmp     loc_1800345A8
0x1800344eb  test    rdi, rdi
0x1800344ee  jz      short loc_180034514
0x1800344f0  mov     r9, rdi
0x1800344f3  lea     r8, aS_2; "%s\\"
0x1800344fa  mov     rdx, rsi; unsigned __int64
0x1800344fd  mov     rcx, rbx; unsigned __int16 *
0x180034500  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034505  test    eax, eax
0x180034507  jns     short loc_180034518
0x180034509  mov     rcx, rbx; pv
0x18003450c  call    cs:__imp_CoTaskMemFree
0x180034512  jmp     short loc_1800344E4
0x180034514  mov     [rax], r12w
0x180034518  mov     r8, r14; unsigned __int16 *
0x18003451b  mov     rdx, rsi; unsigned __int64
0x18003451e  mov     rcx, rbx; unsigned __int16 *
0x180034521  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180034526  test    eax, eax
0x180034528  js      short loc_180034509
0x18003452a  mov     rcx, rbx; Str
0x18003452d  call    ?SetAccountRights@@YAJPEBG0@Z; SetAccountRights(ushort const *,ushort const *)
0x180034532  mov     ebp, eax
0x180034534  test    eax, eax
0x180034536  js      short loc_180034509
0x180034538  mov     [rsp+88h+var_38], r12
0x18003453d  lea     rax, [rsp+88h+hObject]
0x180034545  mov     [rsp+88h+var_40], r12
0x18003454a  mov     r9d, 4
0x180034550  mov     [rsp+88h+var_48], r12
0x180034555  mov     r8, r15
0x180034558  mov     [rsp+88h+var_50], r12
0x18003455d  mov     rdx, rdi
0x180034560  mov     [rsp+88h+var_58], rax
0x180034565  mov     rcx, r14
0x180034568  mov     [rsp+88h+var_60], r12
0x18003456d  mov     [rsp+88h+var_68], r12d
0x180034572  call    cs:__imp_LogonUserExExW
0x180034578  mov     esi, eax
0x18003457a  test    ebp, ebp
0x18003457c  jnz     short loc_180034586
0x18003457e  mov     rcx, rbx; Str
0x180034581  call    ?RemoveAccountRights@@YAJPEBG0@Z; RemoveAccountRights(ushort const *,ushort const *)
0x180034586  mov     rcx, rbx; pv
0x180034589  call    cs:__imp_CoTaskMemFree
0x18003458f  test    esi, esi
0x180034591  jz      short loc_1800345A6
0x180034593  mov     rcx, [rsp+88h+hObject]; hObject
0x18003459b  test    rcx, rcx
0x18003459e  jz      short loc_1800345A6
0x1800345a0  call    cs:__imp_CloseHandle
0x1800345a6  mov     eax, esi
0x1800345a8  lea     r11, [rsp+88h+var_28]
0x1800345ad  mov     rbx, [r11+30h]
0x1800345b1  mov     rbp, [r11+38h]
0x1800345b5  mov     rsp, r11
0x1800345b8  pop     r15
0x1800345ba  pop     r14
0x1800345bc  pop     r12
0x1800345be  pop     rdi
0x1800345bf  pop     rsi
0x1800345c0  retn
```
