# DllGetClassObject

- ea: `0x180007290`
- end: `0x180007374`
- name: `DllGetClassObject`
- size: `228`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007290`
- `0x18000737c`
- `0x180009ef8`
- `0x18000cf30`
- `0x18001b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  __int64 v6; // rax
  CScheduleCF *v7; // rax
  CScheduleCF *v8; // rax
  CScheduleCF *v9; // rdi
  HRESULT v10; // ebx
  CJobCF *v12; // rax

  *ppv = 0;
  v5 = *(_QWORD *)&CLSID_CTask.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_CTask.Data1 == *(_QWORD *)&rclsid->Data1 )
    v5 = *(_QWORD *)CLSID_CTask.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v5 )
  {
    v12 = (CJobCF *)operator new(0x10u);
    if ( v12 )
    {
      v8 = CJobCF::CJobCF(v12);
      v9 = v8;
      if ( v8 )
        goto LABEL_9;
    }
LABEL_11:
    *ppv = 0;
    return -2147024882;
  }
  v6 = *(_QWORD *)&CLSID_CTaskScheduler.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_CTaskScheduler.Data1 == *(_QWORD *)&rclsid->Data1 )
    v6 = *(_QWORD *)CLSID_CTaskScheduler.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v6 )
  {
    v7 = (CScheduleCF *)operator new(0x10u);
    if ( v7 )
    {
      v8 = CScheduleCF::CScheduleCF(v7);
      v9 = v8;
      if ( v8 )
      {
LABEL_9:
        v10 = (**(__int64 (__fastcall ***)(CScheduleCF *, const IID *const, LPVOID *))v8)(v9, riid, ppv);
        (*(void (__fastcall **)(CScheduleCF *))(*(_QWORD *)v9 + 16LL))(v9);
        return v10;
      }
    }
    goto LABEL_11;
  }
  return -2147221231;
}

```

## disassembly

```asm
0x180007290  mov     [rsp+arg_8], rbx
0x180007295  mov     [rsp+arg_10], rbp
0x18000729a  push    rsi
0x18000729b  sub     rsp, 20h
0x18000729f  xor     ebp, ebp
0x1800072a1  mov     rbx, r8
0x1800072a4  mov     [r8], rbp
0x1800072a7  mov     rsi, rdx
0x1800072aa  mov     rax, qword ptr cs:CLSID_CTask.Data1
0x1800072b1  sub     rax, [rcx]
0x1800072b4  jnz     short loc_1800072C1
0x1800072b6  mov     rax, qword ptr cs:CLSID_CTask.Data4
0x1800072bd  sub     rax, [rcx+8]
0x1800072c1  mov     [rsp+28h+arg_0], rdi
0x1800072c6  test    rax, rax
0x1800072c9  jz      short loc_18000732F
0x1800072cb  mov     rax, qword ptr cs:CLSID_CTaskScheduler.Data1
0x1800072d2  sub     rax, [rcx]
0x1800072d5  jnz     short loc_1800072E2
0x1800072d7  mov     rax, qword ptr cs:CLSID_CTaskScheduler.Data4
0x1800072de  sub     rax, [rcx+8]
0x1800072e2  test    rax, rax
0x1800072e5  jnz     short loc_18000735B
0x1800072e7  mov     ecx, 10h; Size
0x1800072ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800072f1  test    rax, rax
0x1800072f4  jz      short loc_18000733E
0x1800072f6  mov     rcx, rax; this
0x1800072f9  call    ??0CScheduleCF@@QEAA@XZ; CScheduleCF::CScheduleCF(void)
0x1800072fe  mov     rdi, rax
0x180007301  test    rax, rax
0x180007304  jz      short loc_18000733E
0x180007306  mov     rcx, [rax]
0x180007309  mov     r8, rbx
0x18000730c  mov     rdx, rsi
0x18000730f  mov     rax, [rcx]
0x180007312  mov     rcx, rdi
0x180007315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000731a  mov     rcx, [rdi]
0x18000731d  mov     ebx, eax
0x18000731f  mov     rax, [rcx+10h]
0x180007323  mov     rcx, rdi
0x180007326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000732b  mov     eax, ebx
0x18000732d  jmp     short loc_180007346
0x18000732f  mov     ecx, 10h; Size
0x180007334  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007339  test    rax, rax
0x18000733c  jnz     short loc_180007362
0x18000733e  mov     [rbx], rbp
0x180007341  mov     eax, 8007000Eh
0x180007346  mov     rdi, [rsp+28h+arg_0]
0x18000734b  mov     rbx, [rsp+28h+arg_8]
0x180007350  mov     rbp, [rsp+28h+arg_10]
0x180007355  add     rsp, 20h
0x180007359  pop     rsi
0x18000735a  retn
0x18000735b  mov     eax, 80040111h
0x180007360  jmp     short loc_180007346
0x180007362  mov     rcx, rax; this
0x180007365  call    ??0CJobCF@@QEAA@XZ; CJobCF::CJobCF(void)
0x18000736a  mov     rdi, rax
0x18000736d  test    rax, rax
0x180007370  jz      short loc_18000733E
0x180007372  jmp     short loc_180007306
```
