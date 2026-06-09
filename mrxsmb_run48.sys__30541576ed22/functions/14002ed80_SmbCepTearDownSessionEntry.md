# SmbCepTearDownSessionEntry

- ea: `0x14002ed80`
- end: `0x14002eeaa`
- name: `SmbCepTearDownSessionEntry`
- size: `298`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140014400`
- `0x140018d50`
- `0x14001c0f0`
- `0x140026d60`
- `0x14002ed80`
- `0x1400383d0`
- `0x140059ea0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ee46`
- `rdbss!RxTearDownDiagnosticLogger` at `0x14002ee69`
- `rdbss!RxTearDownDiagnosticLogger` at `0x14002ee69`
- `rdbss!RxFinalizeSecurityContext` at `0x14002edef`
- `rdbss!RxFinalizeSecurityContext` at `0x14002edef`

## pseudocode

```c
void __fastcall SmbCepTearDownSessionEntry(_QWORD *Context)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rcx
  char *v7; // rax
  void *v8; // rcx

  v1 = Context[3];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids, Context);
  }
  (*(void (__fastcall **)(_QWORD *))(*(_QWORD *)(Context[48] + 56LL) + 768LL))(Context);
  UninitializeSecurityContextForSession((__int64)Context, v3, v4);
  RxFinalizeSecurityContext(Context + 12);
  SmbCeDereferenceServerEntryEx(Context[48], 0, v5);
  v6 = 16;
  Context[48] = 0;
  v7 = (char *)(Context + 76);
  do
  {
    *v7++ = 0;
    --v6;
  }
  while ( v6 );
  if ( Context[74] )
  {
    v8 = (void *)Context[74];
    if ( v8 )
      ExFreePoolWithTag(v8, 0x6D537353u);
    Context[74] = 0;
    *((_DWORD *)Context + 146) = 0;
  }
  RxTearDownDiagnosticLogger(Context[2]);
  SmbCeDecrementTeardownOpCounterAndUnblockWaiters(v1, Context, 2);
  memset(Context, 0, 0x2C0u);
  SmbMmFreeObjectPool(Context);
}

```

## disassembly

```asm
0x14002ed80  mov     [rsp+arg_0], rbx
0x14002ed85  push    rdi
0x14002ed86  sub     rsp, 20h
0x14002ed8a  mov     rdi, [rcx+18h]
0x14002ed8e  mov     rbx, rcx
0x14002ed91  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ed98  lea     rax, WPP_GLOBAL_Control
0x14002ed9f  cmp     rcx, rax
0x14002eda2  jz      short loc_14002EDC9
0x14002eda4  mov     eax, [rcx+2Ch]
0x14002eda7  test    al, 40h
0x14002eda9  jz      short loc_14002EDC9
0x14002edab  cmp     byte ptr [rcx+29h], 2
0x14002edaf  jb      short loc_14002EDC9
0x14002edb1  mov     rcx, [rcx+18h]
0x14002edb5  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002edbc  mov     edx, 17h
0x14002edc1  mov     r9, rbx
0x14002edc4  call    WPP_SF_q
0x14002edc9  mov     rax, [rbx+180h]
0x14002edd0  mov     rcx, [rax+38h]
0x14002edd4  mov     rax, [rcx+300h]
0x14002eddb  mov     rcx, rbx
0x14002edde  call    _guard_dispatch_icall
0x14002ede3  mov     rcx, rbx
0x14002ede6  call    UninitializeSecurityContextForSession
0x14002edeb  lea     rcx, [rbx+60h]
0x14002edef  call    cs:__imp_RxFinalizeSecurityContext
0x14002edf6  nop     dword ptr [rax+rax+00h]
0x14002edfb  mov     rcx, [rbx+180h]; BugCheckParameter2
0x14002ee02  xor     edx, edx
0x14002ee04  call    SmbCeDereferenceServerEntryEx
0x14002ee09  mov     ecx, 10h
0x14002ee0e  mov     qword ptr [rbx+180h], 0
0x14002ee19  lea     rax, [rbx+260h]
0x14002ee20  mov     byte ptr [rax], 0
0x14002ee23  inc     rax
0x14002ee26  sub     rcx, 1
0x14002ee2a  jnz     short loc_14002EE20
0x14002ee2c  cmp     [rbx+250h], rcx
0x14002ee33  jz      short loc_14002EE65
0x14002ee35  mov     rcx, [rbx+250h]; P
0x14002ee3c  test    rcx, rcx
0x14002ee3f  jz      short loc_14002EE52
0x14002ee41  mov     edx, 6D537353h; Tag
0x14002ee46  call    cs:__imp_ExFreePoolWithTag
0x14002ee4d  nop     dword ptr [rax+rax+00h]
0x14002ee52  xor     eax, eax
0x14002ee54  mov     qword ptr [rbx+250h], 0
0x14002ee5f  mov     [rbx+248h], eax
0x14002ee65  mov     rcx, [rbx+10h]
0x14002ee69  call    cs:__imp_RxTearDownDiagnosticLogger
0x14002ee70  nop     dword ptr [rax+rax+00h]
0x14002ee75  mov     r8d, 2
0x14002ee7b  mov     rdx, rbx
0x14002ee7e  mov     rcx, rdi
0x14002ee81  call    SmbCeDecrementTeardownOpCounterAndUnblockWaiters
0x14002ee86  xor     edx, edx; Val
0x14002ee88  mov     r8d, 2C0h; Size
0x14002ee8e  mov     rcx, rbx; void *
0x14002ee91  call    memset
0x14002ee96  mov     rcx, rbx
0x14002ee99  call    SmbMmFreeObjectPool
0x14002ee9e  mov     rbx, [rsp+28h+arg_0]
0x14002eea3  add     rsp, 20h
0x14002eea7  pop     rdi
0x14002eea8  retn
```
