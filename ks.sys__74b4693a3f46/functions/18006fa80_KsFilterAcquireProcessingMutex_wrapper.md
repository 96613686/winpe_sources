# KsFilterAcquireProcessingMutex_wrapper

- ea: `0x18006fa80`
- end: `0x18006fd7e`
- name: `KsFilterAcquireProcessingMutex_wrapper`
- size: `766`
- prototype: `__int64 __fastcall(PKSFILTER Filter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019c60`
- `0x180065c00`
- `0x18006fa80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006fab7`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006fab7`

## string_xrefs

- `0x18006fb8c`: `The driver attempts to acquire the processing mutex while holding it. This operation will cause a deadlock.`

## pseudocode

```c
__int64 __fastcall KsFilterAcquireProcessingMutex_wrapper(PKSFILTER Filter, __int64 a2, __int64 a3, __int64 a4)
{
  const KSFILTER_DESCRIPTOR *Descriptor; // rax
  __int64 v5; // rdi
  const KSTOPOLOGY_CONNECTION *Connections; // r14
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // rbx
  __int64 result; // rax
  __int64 v13; // [rsp+20h] [rbp-20h]
  char v14; // [rsp+20h] [rbp-20h]
  int v15; // [rsp+20h] [rbp-20h]
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF

  Descriptor = Filter[1].Descriptor;
  v5 = 0;
  v16 = 0;
  Connections = Descriptor[1].Connections;
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterAcquireProcessingMutex should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v5 = (*(__int64 (__fastcall **)(const KSTOPOLOGY_CONNECTION *))(KsVerifierUtilTable + 8))(Connections);
    (*(void (__fastcall **)(const KSTOPOLOGY_CONNECTION *))(KsVerifierUtilTable + 72))(Connections);
  }
  if ( (KsXdvExtLevel & 8) != 0 )
  {
    if ( v5 )
    {
      LOBYTE(a4) = 1;
      v14 = 1;
      (*(void (__fastcall **)(_QWORD, __int64, PKSFILTER, __int64, char, __int64 *))(KsVerifierUtilTable + 32))(
        *(_QWORD *)(v5 + 160),
        136,
        Filter,
        a4,
        v14,
        &v16);
      if ( v16 )
      {
        if ( *(struct _KTHREAD **)(v16 + 112) == KeGetCurrentThread() && *(_BYTE *)(v16 + 128) == 1 )
        {
          v13 = v5 + 160;
          (*(void (__fastcall **)(const char *, __int64, __int64))(KsVerifierUtilTable + 88))(
            "The driver attempts to acquire the processing mutex while holding it. This operation will cause a deadlock.",
            528395,
            v5);
        }
      }
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(const KSTOPOLOGY_CONNECTION *))(KsVerifierUtilTable + 80))(Connections);
  KsFilterAcquireProcessingMutex(Filter);
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(const KSTOPOLOGY_CONNECTION *))(KsVerifierUtilTable + 72))(Connections);
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(v8) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSFILTER, __int64, __int64 *))(KsVerifierUtilTable + 24))(
      v5 + 144,
      144,
      Filter,
      v8,
      &v16);
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSFILTER, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 160,
      136,
      Filter,
      v9,
      &v16);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(v8) = 1;
    LOBYTE(v13) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSFILTER, __int64, __int64, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v5 + 144),
      144,
      Filter,
      v8,
      v13,
      &v16);
    if ( v16 )
    {
      *(_QWORD *)(v16 + 120) = Filter;
      *(_BYTE *)(v16 + 128) = 1;
      *(_QWORD *)(v16 + 112) = KeGetCurrentThread();
      *(_DWORD *)(v16 + 136) = XDV_KS_PROCESSING_MUTEX_TIMELIMIT;
      v11 = v16;
      *(_DWORD *)(v11 + 132) = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 120))(3);
    }
    LOBYTE(v10) = 1;
    LOBYTE(v15) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSFILTER, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v5 + 160),
      136,
      Filter,
      v10,
      v15,
      &v16);
    if ( v16 )
    {
      *(_QWORD *)(v16 + 120) = Filter;
      *(_BYTE *)(v16 + 128) = 1;
      *(_QWORD *)(v16 + 112) = KeGetCurrentThread();
    }
  }
  result = (unsigned int)KsXdvExtLevel;
  if ( (KsXdvExtLevel & 0x18) != 0 )
    return (*(__int64 (__fastcall **)(const KSTOPOLOGY_CONNECTION *))(KsVerifierUtilTable + 80))(Connections);
  return result;
}

```

## disassembly

```asm
0x18006fa80  mov     [rsp-18h+arg_8], rbx
0x18006fa85  mov     [rsp-18h+arg_10], rsi
0x18006fa8a  push    rbp
0x18006fa8b  push    rdi
0x18006fa8c  push    r14
0x18006fa8e  mov     rbp, rsp
0x18006fa91  sub     rsp, 40h
0x18006fa95  mov     rax, [rcx+18h]
0x18006fa99  xor     edi, edi
0x18006fa9b  mov     [rbp+arg_0], 0
0x18006faa3  mov     rsi, rcx
0x18006faa6  mov     r14, [rax+0C0h]
0x18006faad  mov     eax, cs:KsXdvExtLevel
0x18006fab3  test    al, 8
0x18006fab5  jz      short loc_18006FAE3
0x18006fab7  call    cs:__imp_KeGetCurrentIrql
0x18006fabe  nop     dword ptr [rax+rax+00h]
0x18006fac3  test    al, al
0x18006fac5  jz      short loc_18006FAE3
0x18006fac7  mov     rax, cs:KsVerifierUtilTable
0x18006face  lea     rcx, aKsfilteracquir; "KsFilterAcquireProcessingMutex should o"...
0x18006fad5  mov     edx, 81009h
0x18006fada  mov     rax, [rax+60h]
0x18006fade  call    _guard_dispatch_icall
0x18006fae3  mov     eax, cs:KsXdvExtLevel
0x18006fae9  test    al, 18h
0x18006faeb  jz      short loc_18006FB16
0x18006faed  mov     rax, cs:KsVerifierUtilTable
0x18006faf4  mov     rcx, r14
0x18006faf7  mov     rax, [rax+8]
0x18006fafb  call    _guard_dispatch_icall
0x18006fb00  mov     rcx, cs:KsVerifierUtilTable
0x18006fb07  mov     rdi, rax
0x18006fb0a  mov     rax, [rcx+48h]
0x18006fb0e  mov     rcx, r14
0x18006fb11  call    _guard_dispatch_icall
0x18006fb16  mov     ecx, cs:KsXdvExtLevel
0x18006fb1c  test    cl, 8
0x18006fb1f  jz      loc_18006FBB1
0x18006fb25  test    rdi, rdi
0x18006fb28  jz      loc_18006FBB1
0x18006fb2e  mov     rax, cs:KsVerifierUtilTable
0x18006fb35  lea     rcx, [rbp+arg_0]
0x18006fb39  mov     [rsp+40h+var_18], rcx
0x18006fb3e  lea     rbx, [rdi+0A0h]
0x18006fb45  mov     rcx, [rbx]
0x18006fb48  mov     r9b, 1
0x18006fb4b  mov     r8, rsi
0x18006fb4e  mov     byte ptr [rsp+40h+var_20], 1
0x18006fb53  mov     rax, [rax+20h]
0x18006fb57  mov     edx, 88h
0x18006fb5c  call    _guard_dispatch_icall
0x18006fb61  cmp     [rbp+arg_0], 0
0x18006fb66  jz      short loc_18006FBB1
0x18006fb68  mov     rax, gs:188h
0x18006fb71  mov     r9, [rbp+arg_0]
0x18006fb75  cmp     [r9+70h], rax
0x18006fb79  jnz     short loc_18006FBB1
0x18006fb7b  cmp     byte ptr [r9+80h], 1
0x18006fb83  jnz     short loc_18006FBB1
0x18006fb85  mov     rax, cs:KsVerifierUtilTable
0x18006fb8c  lea     rcx, aTheDriverAttem_2; "The driver attempts to acquire the proc"...
0x18006fb93  mov     dword ptr [rsp+40h+var_18], 88h
0x18006fb9b  mov     r8, rdi
0x18006fb9e  mov     edx, 8100Bh
0x18006fba3  mov     [rsp+40h+var_20], rbx
0x18006fba8  mov     rax, [rax+58h]
0x18006fbac  call    _guard_dispatch_icall
0x18006fbb1  mov     eax, cs:KsXdvExtLevel
0x18006fbb7  test    al, 18h
0x18006fbb9  jz      short loc_18006FBCE
0x18006fbbb  mov     rax, cs:KsVerifierUtilTable
0x18006fbc2  mov     rcx, r14
0x18006fbc5  mov     rax, [rax+50h]
0x18006fbc9  call    _guard_dispatch_icall
0x18006fbce  mov     rcx, rsi; Filter
0x18006fbd1  call    KsFilterAcquireProcessingMutex
0x18006fbd6  mov     eax, cs:KsXdvExtLevel
0x18006fbdc  test    al, 18h
0x18006fbde  jz      short loc_18006FBF3
0x18006fbe0  mov     rax, cs:KsVerifierUtilTable
0x18006fbe7  mov     rcx, r14
0x18006fbea  mov     rax, [rax+48h]
0x18006fbee  call    _guard_dispatch_icall
0x18006fbf3  mov     eax, cs:KsXdvExtLevel
0x18006fbf9  mov     ebx, 90h
0x18006fbfe  test    al, 8
0x18006fc00  jz      short loc_18006FC58
0x18006fc02  test    rdi, rdi
0x18006fc05  jz      short loc_18006FC58
0x18006fc07  mov     rax, cs:KsVerifierUtilTable
0x18006fc0e  lea     rdx, [rbp+arg_0]
0x18006fc12  mov     [rsp+40h+var_20], rdx
0x18006fc17  lea     rcx, [rdi+90h]
0x18006fc1e  mov     r9b, 1
0x18006fc21  mov     r8, rsi
0x18006fc24  mov     edx, ebx
0x18006fc26  mov     rax, [rax+18h]
0x18006fc2a  call    _guard_dispatch_icall
0x18006fc2f  mov     rax, cs:KsVerifierUtilTable
0x18006fc36  lea     rdx, [rbp+arg_0]
0x18006fc3a  mov     [rsp+40h+var_20], rdx
0x18006fc3f  lea     rcx, [rdi+0A0h]
0x18006fc46  mov     r9b, 1
0x18006fc49  lea     edx, [rbx-8]
0x18006fc4c  mov     r8, rsi
0x18006fc4f  mov     rax, [rax+28h]
0x18006fc53  call    _guard_dispatch_icall
0x18006fc58  mov     eax, cs:KsXdvExtLevel
0x18006fc5e  test    al, 8
0x18006fc60  jz      loc_18006FD4D
0x18006fc66  test    rdi, rdi
0x18006fc69  jz      loc_18006FD4D
0x18006fc6f  mov     rax, cs:KsVerifierUtilTable
0x18006fc76  lea     rcx, [rbp+arg_0]
0x18006fc7a  mov     [rsp+40h+var_18], rcx
0x18006fc7f  mov     r9b, 1
0x18006fc82  mov     rcx, [rdi+90h]
0x18006fc89  mov     r8, rsi
0x18006fc8c  mov     edx, ebx
0x18006fc8e  mov     byte ptr [rsp+40h+var_20], 1
0x18006fc93  mov     rax, [rax+20h]
0x18006fc97  call    _guard_dispatch_icall
0x18006fc9c  mov     rax, [rbp+arg_0]
0x18006fca0  test    rax, rax
0x18006fca3  jz      short loc_18006FCF4
0x18006fca5  mov     [rax+78h], rsi
0x18006fca9  mov     rax, [rbp+arg_0]
0x18006fcad  mov     byte ptr [rax+80h], 1
0x18006fcb4  mov     rcx, gs:188h
0x18006fcbd  mov     rax, [rbp+arg_0]
0x18006fcc1  mov     [rax+70h], rcx
0x18006fcc5  mov     rcx, [rbp+arg_0]
0x18006fcc9  mov     eax, cs:XDV_KS_PROCESSING_MUTEX_TIMELIMIT
0x18006fccf  mov     [rcx+88h], eax
0x18006fcd5  mov     ecx, 3
0x18006fcda  mov     rax, cs:KsVerifierUtilTable
0x18006fce1  mov     rbx, [rbp+arg_0]
0x18006fce5  mov     rax, [rax+78h]
0x18006fce9  call    _guard_dispatch_icall
0x18006fcee  mov     [rbx+84h], eax
0x18006fcf4  mov     rax, cs:KsVerifierUtilTable
0x18006fcfb  lea     rcx, [rbp+arg_0]
0x18006fcff  mov     [rsp+40h+var_18], rcx
0x18006fd04  mov     r9b, 1
0x18006fd07  mov     rcx, [rdi+0A0h]
0x18006fd0e  mov     r8, rsi
0x18006fd11  mov     edx, 88h
0x18006fd16  mov     byte ptr [rsp+40h+var_20], 1
0x18006fd1b  mov     rax, [rax+20h]
0x18006fd1f  call    _guard_dispatch_icall
0x18006fd24  mov     rax, [rbp+arg_0]
0x18006fd28  test    rax, rax
0x18006fd2b  jz      short loc_18006FD4D
0x18006fd2d  mov     [rax+78h], rsi
0x18006fd31  mov     rax, [rbp+arg_0]
0x18006fd35  mov     byte ptr [rax+80h], 1
0x18006fd3c  mov     rdx, gs:188h
0x18006fd45  mov     rax, [rbp+arg_0]
0x18006fd49  mov     [rax+70h], rdx
0x18006fd4d  mov     eax, cs:KsXdvExtLevel
0x18006fd53  test    al, 18h
0x18006fd55  jz      short loc_18006FD6A
0x18006fd57  mov     rax, cs:KsVerifierUtilTable
0x18006fd5e  mov     rcx, r14
0x18006fd61  mov     rax, [rax+50h]
0x18006fd65  call    _guard_dispatch_icall
0x18006fd6a  mov     rbx, [rsp+40h+arg_8]
0x18006fd6f  mov     rsi, [rsp+40h+arg_10]
0x18006fd74  add     rsp, 40h
0x18006fd78  pop     r14
0x18006fd7a  pop     rdi
0x18006fd7b  pop     rbp
0x18006fd7c  retn
```
