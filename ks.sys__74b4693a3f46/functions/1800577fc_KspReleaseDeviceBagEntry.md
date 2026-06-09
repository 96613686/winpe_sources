# KspReleaseDeviceBagEntry

- ea: `0x1800577fc`
- end: `0x180057940`
- name: `KspReleaseDeviceBagEntry`
- size: `324`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18004ee10`
- `0x1800573f0`
- `0x1800576d4`

## callees

- `0x18000a2d4`
- `0x18000b7bc`
- `0x18000dddc`
- `0x180019c60`
- `0x1800577fc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800578c4`
- `ntoskrnl!KeReleaseMutex` at `0x1800578c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x180057851`
- `ntoskrnl!KeWaitForSingleObject` at `0x180057851`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800578e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800578e4`

## pseudocode

```c
__int64 __fastcall KspReleaseDeviceBagEntry(__int64 a1, _DWORD *a2, char a3)
{
  _DWORD *v4; // rbx
  int v6; // edx
  unsigned int v7; // edi
  void (__fastcall *v8)(void *); // rax
  void *v9; // rcx
  _QWORD *v10; // rax
  void **v11; // rcx

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      60,
      (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
  }
  KeWaitForSingleObject((PVOID)(a1 + 16), Executive, 0, 0, 0);
  v7 = v4[8];
  v4[8] = v7 - 1;
  if ( v7 == 1 && a3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        61,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        *((_QWORD *)v4 + 2));
    }
    v8 = (void (__fastcall *)(void *))*((_QWORD *)v4 + 3);
    v9 = (void *)*((_QWORD *)v4 + 2);
    if ( v8 )
      v8(v9);
    else
      ExFreePoolWithTag(v9, 0);
    v10 = *(_QWORD **)v4;
    if ( *(_DWORD **)(*(_QWORD *)v4 + 8LL) != v4 || (v11 = (void **)*((_QWORD *)v4 + 1), *v11 != v4) )
      __fastfail(3u);
    *v11 = v10;
    v10[1] = v11;
    operator delete(v4);
  }
  KeReleaseMutex((PRKMUTEX)(a1 + 16), 0);
  return v7;
}

```

## disassembly

```asm
0x1800577fc  push    rbx
0x1800577fe  push    rbp
0x1800577ff  push    rsi
0x180057800  push    rdi
0x180057801  push    r13
0x180057803  push    r14
0x180057805  push    r15
0x180057807  sub     rsp, 30h
0x18005780b  mov     sil, r8b
0x18005780e  mov     rbx, rdx
0x180057811  mov     rbp, rcx
0x180057814  lea     r15, WPP_RECORDER_INITIALIZED
0x18005781b  xor     r14d, r14d
0x18005781e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180057825  lea     r13, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x18005782c  jz      short loc_180057840
0x18005782e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057835  cmp     [rcx+48h], r14w
0x18005783a  jnz     loc_1800578F9
0x180057840  xor     r9d, r9d; Alertable
0x180057843  mov     [rsp+68h+Timeout], r14; Timeout
0x180057848  xor     r8d, r8d; WaitMode
0x18005784b  lea     rcx, [rbp+10h]; Object
0x18005784f  xor     edx, edx; WaitReason
0x180057851  call    cs:__imp_KeWaitForSingleObject
0x180057858  nop     dword ptr [rax+rax+00h]
0x18005785d  mov     edi, [rbx+20h]
0x180057860  lea     eax, [rdi-1]
0x180057863  mov     [rbx+20h], eax
0x180057866  cmp     edi, 1
0x180057869  jnz     short loc_1800578BE
0x18005786b  test    sil, sil
0x18005786e  jz      short loc_1800578BE
0x180057870  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180057877  jz      short loc_18005788B
0x180057879  mov     rcx, cs:WPP_GLOBAL_Control
0x180057880  cmp     [rcx+48h], r14w
0x180057885  jnz     loc_180057918
0x18005788b  mov     rax, [rbx+18h]
0x18005788f  mov     rcx, [rbx+10h]; P
0x180057893  test    rax, rax
0x180057896  jz      short loc_1800578E2
0x180057898  call    _guard_dispatch_icall
0x18005789d  mov     rax, [rbx]
0x1800578a0  cmp     [rax+8], rbx
0x1800578a4  jnz     short loc_1800578F2
0x1800578a6  mov     rcx, [rbx+8]
0x1800578aa  cmp     [rcx], rbx
0x1800578ad  jnz     short loc_1800578F2
0x1800578af  mov     [rcx], rax
0x1800578b2  mov     [rax+8], rcx
0x1800578b6  mov     rcx, rbx; void *
0x1800578b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800578be  xor     edx, edx; Wait
0x1800578c0  lea     rcx, [rbp+10h]; Mutex
0x1800578c4  call    cs:__imp_KeReleaseMutex
0x1800578cb  nop     dword ptr [rax+rax+00h]
0x1800578d0  mov     eax, edi
0x1800578d2  add     rsp, 30h
0x1800578d6  pop     r15
0x1800578d8  pop     r14
0x1800578da  pop     r13
0x1800578dc  pop     rdi
0x1800578dd  pop     rsi
0x1800578de  pop     rbp
0x1800578df  pop     rbx
0x1800578e0  retn
0x1800578e2  xor     edx, edx; Tag
0x1800578e4  call    cs:__imp_ExFreePoolWithTag
0x1800578eb  nop     dword ptr [rax+rax+00h]
0x1800578f0  jmp     short loc_18005789D
0x1800578f2  mov     ecx, 3
0x1800578f7  int     29h; Win8: RtlFailFast(ecx)
0x1800578f9  mov     rcx, [rcx+40h]
0x1800578fd  mov     r9d, 3Ch ; '<'
0x180057903  mov     dl, 5
0x180057905  mov     [rsp+68h+Timeout], r13
0x18005790a  lea     r8d, [r9-3Bh]
0x18005790e  call    WPP_RECORDER_SF_
0x180057913  jmp     loc_180057840
0x180057918  mov     rax, [rbx+10h]
0x18005791c  mov     r9d, 3Dh ; '='
0x180057922  mov     rcx, [rcx+40h]
0x180057926  mov     dl, 5
0x180057928  mov     [rsp+68h+var_40], rax
0x18005792d  mov     [rsp+68h+Timeout], r13
0x180057932  lea     r8d, [r9-3Ch]
0x180057936  call    WPP_RECORDER_SF_q
0x18005793b  jmp     loc_18005788B
```
