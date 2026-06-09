# GetNGenQueueMSIKey(NewHolder<IRegWrapper> &,NewHolder<IRegWrapper::Key> &)

- ea: `0x180011cf8`
- end: `0x180011e59`
- name: `?GetNGenQueueMSIKey@@YAHAEAV?$NewHolder@VIRegWrapper@@@@AEAV?$NewHolder@VKey@IRegWrapper@@@@@Z`
- size: `353`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180012540`
- `0x180012884`

## callees

- `0x180001e8c`
- `0x180011cf8`
- `0x1800199ec`
- `0x180030ab8`
- `0x180030d84`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180011e2a`
- `KERNEL32!HeapFree` at `0x180011e2a`
- `KERNEL32!GetProcessHeap` at `0x180011e15`
- `KERNEL32!GetProcessHeap` at `0x180011e15`

## string_xrefs

- `0x180011d96`: `NGenQueueMSI`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
_BOOL8 __fastcall GetNGenQueueMSIKey(__int64 a1, __int64 a2)
{
  struct IRegWrapper *NGenQueueRegWrapper; // rdi
  BOOL v5; // edi
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+24h] [rbp-DCh]
  LPVOID lpMem; // [rsp+30h] [rbp-D0h]
  __int16 v12; // [rsp+38h] [rbp-C8h] BYREF

  NGenQueueRegWrapper = CreateNGenQueueRegWrapper();
  if ( *(_DWORD *)(a1 + 8) )
  {
    if ( *(_QWORD *)a1 )
      (***(void (__fastcall ****)(_QWORD, __int64))a1)(*(_QWORD *)a1, 1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  *(_QWORD *)a1 = NGenQueueRegWrapper;
  if ( NGenQueueRegWrapper )
    *(_DWORD *)(a1 + 8) = 1;
  v10 = 512;
  lpMem = &v12;
  v9 = 2;
  v12 = 0;
  SString::Set((SString *)&v9, L"NGenQueueMSI");
  SString::Append((SString *)&v9, L"\\WIN64");
  SString::Append((SString *)&v9, L"\\Default");
  SString::ConvertToUnicode((SString *)&v9);
  v5 = (*(unsigned __int8 (__fastcall **)(_QWORD, LPVOID, __int64))(**(_QWORD **)(*(_QWORD *)a1 + 8LL) + 8LL))(
         *(_QWORD *)(*(_QWORD *)a1 + 8LL),
         lpMem,
         a2) != 0;
  if ( (v10 & 0x800000000LL) != 0 )
  {
    v6 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180011cf8  mov     [rsp-8+arg_10], rbx
0x180011cfd  mov     [rsp-8+arg_18], rsi
0x180011d02  push    rbp
0x180011d03  push    rdi
0x180011d04  push    r14
0x180011d06  lea     rbp, [rsp-150h]
0x180011d0e  sub     rsp, 250h
0x180011d15  mov     rax, cs:__security_cookie
0x180011d1c  xor     rax, rsp
0x180011d1f  mov     [rbp+160h+var_20], rax
0x180011d26  mov     rsi, rdx
0x180011d29  mov     rbx, rcx
0x180011d2c  call    ?CreateNGenQueueRegWrapper@@YAPEAVIRegWrapper@@XZ; CreateNGenQueueRegWrapper(void)
0x180011d31  mov     rdi, rax
0x180011d34  xor     r14d, r14d
0x180011d37  cmp     [rbx+8], r14d
0x180011d3b  jz      short loc_180011D59
0x180011d3d  mov     rcx, [rbx]
0x180011d40  test    rcx, rcx
0x180011d43  jz      short loc_180011D55
0x180011d45  mov     rdx, [rcx]
0x180011d48  mov     rax, [rdx]
0x180011d4b  lea     edx, [r14+1]
0x180011d4f  call    cs:__guard_dispatch_icall_fptr
0x180011d55  mov     [rbx+8], r14d
0x180011d59  mov     [rbx], rdi
0x180011d5c  test    rdi, rdi
0x180011d5f  jz      short loc_180011D68
0x180011d61  mov     dword ptr [rbx+8], 1
0x180011d68  mov     [rsp+260h+var_240], r14
0x180011d6d  mov     [rsp+260h+var_240+4], 200h
0x180011d76  mov     [rsp+260h+lpMem], r14
0x180011d7b  lea     rax, [rsp+260h+var_228]
0x180011d80  mov     [rsp+260h+lpMem], rax
0x180011d85  mov     dword ptr [rsp+260h+var_240], 2
0x180011d8d  mov     rax, [rsp+260h+lpMem]
0x180011d92  mov     [rax], r14w
0x180011d96  lea     rdx, aNgenqueuemsi; "NGenQueueMSI"
0x180011d9d  lea     rcx, [rsp+260h+var_240]; this
0x180011da2  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180011da7  lea     rdx, aWin64; "\\WIN64"
0x180011dae  lea     rcx, [rsp+260h+var_240]; this
0x180011db3  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180011db8  lea     rdx, aDefault; "\\Default"
0x180011dbf  lea     rcx, [rsp+260h+var_240]; this
0x180011dc4  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180011dc9  lea     rcx, [rsp+260h+var_240]; this
0x180011dce  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180011dd3  mov     rax, [rbx]
0x180011dd6  mov     rcx, [rax+8]
0x180011dda  mov     rax, [rcx]
0x180011ddd  mov     r8, rsi
0x180011de0  mov     rdx, [rsp+260h+lpMem]
0x180011de5  mov     rax, [rax+8]
0x180011de9  call    cs:__guard_dispatch_icall_fptr
0x180011def  mov     edi, r14d
0x180011df2  test    al, al
0x180011df4  setnz   dil
0x180011df8  test    [rsp+260h+var_238], 8
0x180011dfd  jz      short loc_180011E30
0x180011dff  mov     rbx, [rsp+260h+lpMem]
0x180011e04  test    rbx, rbx
0x180011e07  jz      short loc_180011E30
0x180011e09  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180011e10  test    rax, rax
0x180011e13  jnz     short loc_180011E22
0x180011e15  call    cs:__imp_GetProcessHeap
0x180011e1b  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180011e22  mov     r8, rbx; lpMem
0x180011e25  xor     edx, edx; dwFlags
0x180011e27  mov     rcx, rax; hHeap
0x180011e2a  call    cs:__imp_HeapFree
0x180011e30  mov     eax, edi
0x180011e32  mov     rcx, [rbp+160h+var_20]
0x180011e39  xor     rcx, rsp; StackCookie
0x180011e3c  call    __security_check_cookie
0x180011e41  lea     r11, [rsp+260h+var_10]
0x180011e49  mov     rbx, [r11+30h]
0x180011e4d  mov     rsi, [r11+38h]
0x180011e51  mov     rsp, r11
0x180011e54  pop     r14
0x180011e56  pop     rdi
0x180011e57  pop     rbp
0x180011e58  retn
```
