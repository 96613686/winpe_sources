# ProcessDriverStoreInfsForRemoval

- ea: `0x180007498`
- end: `0x18000754b`
- name: `ProcessDriverStoreInfsForRemoval`
- size: `179`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180006dc4`

## callees

- `0x180007498`
- `0x180008dfe`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800074f0`
- `KERNEL32!GetLastError` at `0x1800074f0`
- `SETUPAPI!pSetupStringTableEnum` at `0x1800074e6`
- `SETUPAPI!pSetupStringTableEnum` at `0x1800074e6`

## pseudocode

```c
__int64 __fastcall ProcessDriverStoreInfsForRemoval(__int64 a1)
{
  DWORD LastError; // eax
  DWORD v3; // edi
  _BYTE v5[160]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(v5, 0, sizeof(v5));
  if ( !(unsigned int)pSetupStringTableEnum(
                        *(_QWORD *)(a1 + 112),
                        v5,
                        160,
                        &StrTabEnumDriverStoreInfForRemovalCallback,
                        a1) )
  {
    LastError = GetLastError();
LABEL_4:
    v3 = LastError;
    (*(void (__fastcall **)(_QWORD, __int64))(a1 + 40))(*(_QWORD *)(a1 + 48), 1);
    return v3;
  }
  LastError = *(_DWORD *)a1;
  v3 = 0;
  if ( *(_DWORD *)a1 )
    goto LABEL_4;
  return v3;
}

```

## disassembly

```asm
0x180007498  mov     [rsp+arg_8], rbx
0x18000749d  push    rdi
0x18000749e  sub     rsp, 0E0h
0x1800074a5  mov     rax, cs:__security_cookie
0x1800074ac  xor     rax, rsp
0x1800074af  mov     [rsp+0E8h+var_18], rax
0x1800074b7  mov     rbx, rcx
0x1800074ba  mov     edi, 0A0h
0x1800074bf  mov     r8d, edi; Size
0x1800074c2  lea     rcx, [rsp+0E8h+var_B8]; void *
0x1800074c7  xor     edx, edx; Val
0x1800074c9  call    memset_0
0x1800074ce  mov     rcx, [rbx+70h]
0x1800074d2  lea     r9, StrTabEnumDriverStoreInfForRemovalCallback
0x1800074d9  mov     r8d, edi
0x1800074dc  mov     [rsp+0E8h+var_C8], rbx
0x1800074e1  lea     rdx, [rsp+0E8h+var_B8]
0x1800074e6  call    cs:__imp_pSetupStringTableEnum
0x1800074ec  test    eax, eax
0x1800074ee  jnz     short loc_1800074FF
0x1800074f0  call    cs:__imp_GetLastError
0x1800074f6  lea     r9, aPsetupstringta_0; "pSetupStringTableEnum StrTabDriverStore"...
0x1800074fd  jmp     short loc_18000750E
0x1800074ff  mov     eax, [rbx]
0x180007501  xor     edi, edi
0x180007503  test    eax, eax
0x180007505  jz      short loc_180007528
0x180007507  lea     r9, aStrtabenumdriv; "StrTabEnumDriverStoreInfForRemovalCallb"...
0x18000750e  mov     rcx, [rbx+30h]
0x180007512  xor     r8d, r8d
0x180007515  mov     edi, eax
0x180007517  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18000751b  mov     rax, [rbx+28h]
0x18000751f  lea     edx, [r8+1]
0x180007523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007528  mov     eax, edi
0x18000752a  mov     rcx, [rsp+0E8h+var_18]
0x180007532  xor     rcx, rsp; StackCookie
0x180007535  call    __security_check_cookie
0x18000753a  mov     rbx, [rsp+0E8h+arg_8]
0x180007542  add     rsp, 0E0h
0x180007549  pop     rdi
0x18000754a  retn
```
