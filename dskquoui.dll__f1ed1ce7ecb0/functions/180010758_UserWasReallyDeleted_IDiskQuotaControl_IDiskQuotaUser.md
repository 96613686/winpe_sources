# UserWasReallyDeleted(IDiskQuotaControl *,IDiskQuotaUser *)

- ea: `0x180010758`
- end: `0x1800108b8`
- name: `?UserWasReallyDeleted@@YA_NPEAUIDiskQuotaControl@@PEAUIDiskQuotaUser@@@Z`
- size: `352`
- prototype: `bool __fastcall(struct IDiskQuotaControl *, struct IDiskQuotaUser *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c8c4`

## callees

- `0x180001510`
- `0x180010758`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010860`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010860`

## pseudocode

```c
char __fastcall UserWasReallyDeleted(struct IDiskQuotaControl *a1, struct IDiskQuotaUser *a2)
{
  char v3; // di
  struct IDiskQuotaControlVtbl *lpVtbl; // rax
  int i; // ebx
  __int64 v7; // [rsp+30h] [rbp-29h] BYREF
  __int64 v8; // [rsp+38h] [rbp-21h] BYREF
  __int64 v9; // [rsp+40h] [rbp-19h] BYREF
  __int64 v10; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v11[80]; // [rsp+50h] [rbp-9h] BYREF

  v3 = 1;
  if ( ((int (__fastcall *)(struct IDiskQuotaUser *, _BYTE *, __int64))a2->lpVtbl->GetQuotaLimit)(a2, v11, 68) >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    v7 = 0;
    if ( ((int (__fastcall *)(struct IDiskQuotaControl *, _BYTE *, _QWORD, __int64 *))lpVtbl->GiveUserNameResolutionPriority)(
           a1,
           v11,
           0,
           &v7) >= 0 )
    {
      for ( i = 0; i <= 1; ++i )
      {
        if ( !v3 )
          break;
        v8 = 0;
        v9 = 0;
        v10 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, &v8);
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 56LL))(v7, &v9);
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 88LL))(v7, &v10);
        if ( v8 == -2 || !v8 && !v9 && v10 == v8 )
        {
          v3 = 1;
          if ( !i )
          {
            Sleep(0x64u);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 128LL))(v7);
          }
        }
        else
        {
          v3 = 0;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180010758  mov     [rsp-8+arg_10], rbx
0x18001075d  mov     [rsp-8+arg_18], rdi
0x180010762  push    rbp
0x180010763  lea     rbp, [rsp-57h]
0x180010768  sub     rsp, 0B0h
0x18001076f  mov     rax, cs:__security_cookie
0x180010776  xor     rax, rsp
0x180010779  mov     [rbp+57h+var_10], rax
0x18001077d  mov     rax, [rdx]
0x180010780  mov     r9, rdx
0x180010783  mov     rbx, rcx
0x180010786  lea     rdx, [rbp+57h+var_60]
0x18001078a  mov     r8d, 44h ; 'D'
0x180010790  mov     rcx, r9
0x180010793  mov     dil, 1
0x180010796  mov     rax, [rax+30h]
0x18001079a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001079f  test    eax, eax
0x1800107a1  js      loc_180010894
0x1800107a7  mov     rax, [rbx]
0x1800107aa  lea     r9, [rbp+57h+var_80]
0x1800107ae  xor     r8d, r8d
0x1800107b1  mov     [rbp+57h+var_80], 0
0x1800107b9  lea     rdx, [rbp+57h+var_60]
0x1800107bd  mov     rcx, rbx
0x1800107c0  mov     rax, [rax+98h]
0x1800107c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107cc  test    eax, eax
0x1800107ce  js      loc_180010894
0x1800107d4  xor     ebx, ebx
0x1800107d6  test    dil, dil
0x1800107d9  jz      loc_180010884
0x1800107df  mov     rcx, [rbp+57h+var_80]
0x1800107e3  lea     rdx, [rbp+57h+var_78]
0x1800107e7  mov     [rbp+57h+var_78], 0
0x1800107ef  mov     [rbp+57h+var_70], 0
0x1800107f7  mov     [rbp+57h+var_68], 0
0x1800107ff  mov     rax, [rcx]
0x180010802  mov     rax, [rax+48h]
0x180010806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080b  mov     rcx, [rbp+57h+var_80]
0x18001080f  lea     rdx, [rbp+57h+var_70]
0x180010813  mov     rax, [rcx]
0x180010816  mov     rax, [rax+38h]
0x18001081a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001081f  mov     rcx, [rbp+57h+var_80]
0x180010823  lea     rdx, [rbp+57h+var_68]
0x180010827  mov     rax, [rcx]
0x18001082a  mov     rax, [rax+58h]
0x18001082e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010833  mov     rax, [rbp+57h+var_78]
0x180010837  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18001083b  jz      short loc_180010853
0x18001083d  test    rax, rax
0x180010840  jnz     short loc_18001084E
0x180010842  cmp     [rbp+57h+var_70], rax
0x180010846  jnz     short loc_18001084E
0x180010848  cmp     [rbp+57h+var_68], rax
0x18001084c  jz      short loc_180010853
0x18001084e  xor     dil, dil
0x180010851  jmp     short loc_180010879
0x180010853  mov     dil, 1
0x180010856  cmp     ebx, 1
0x180010859  jnb     short loc_180010879
0x18001085b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180010860  call    cs:__imp_Sleep
0x180010866  mov     rcx, [rbp+57h+var_80]
0x18001086a  mov     rax, [rcx]
0x18001086d  mov     rax, [rax+80h]
0x180010874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010879  inc     ebx
0x18001087b  cmp     ebx, 1
0x18001087e  jle     loc_1800107D6
0x180010884  mov     rcx, [rbp+57h+var_80]
0x180010888  mov     rdx, [rcx]
0x18001088b  mov     rax, [rdx+10h]
0x18001088f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010894  mov     al, dil
0x180010897  mov     rcx, [rbp+57h+var_10]
0x18001089b  xor     rcx, rsp; StackCookie
0x18001089e  call    __security_check_cookie
0x1800108a3  lea     r11, [rsp+0B0h+var_s0]
0x1800108ab  mov     rbx, [r11+20h]
0x1800108af  mov     rdi, [r11+28h]
0x1800108b3  mov     rsp, r11
0x1800108b6  pop     rbp
0x1800108b7  retn
```
