# QueryNameCompletion

- ea: `0x14000ba70`
- end: `0x14000bbc3`
- name: `QueryNameCompletion`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004880`
- `0x14000b810`
- `0x14000ba70`
- `0x140018818`
- `0x140041e1c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000bb38`
- `ntoskrnl!IofCompleteRequest` at `0x14000bb38`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bada`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bb27`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bb8b`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bada`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bb27`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000bb8b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000ba8d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000bb11`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000ba8d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000bb11`

## pseudocode

```c
__int64 __fastcall QueryNameCompletion(__int64 a1, int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  NTSTATUS NameData; // eax
  KIRQL Irql; // [rsp+40h] [rbp+8h] BYREF
  KIRQL v9; // [rsp+50h] [rbp+18h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v4 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v4 && (v5 = *(_QWORD *)(v4 + 184)) != 0 && *(_QWORD *)(v5 + 32) == a1 )
  {
    *(_QWORD *)(v5 + 32) = 0;
    _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0);
    IoReleaseCancelSpinLock(Irql);
    if ( a2 || (NameData = CopyFindNameData(0, v4, a1), NameData < 0) )
    {
      v9 = 0;
      *(_DWORD *)(v4 + 48) = -1073741643;
      *(_QWORD *)(v4 + 56) = 0;
      if ( SBYTE2(xmmword_140038420) < 0 )
        WPP_SF_qdd(1047, 70, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v4, -1073741643, 0);
      IoAcquireCancelSpinLock(&v9);
      _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0);
      IoReleaseCancelSpinLock(v9);
      IofCompleteRequest((PIRP)v4, 2);
    }
    else
    {
      NTIoComplete((PIRP)v4, NameData, 0xFFFFFFFF);
    }
  }
  else
  {
    IoReleaseCancelSpinLock(Irql);
  }
  return FreeTracker(a1, 4);
}

```

## disassembly

```asm
0x14000ba70  mov     rax, rsp
0x14000ba73  mov     [rax+10h], rbx
0x14000ba77  mov     [rax+20h], rsi
0x14000ba7b  push    rdi
0x14000ba7c  sub     rsp, 30h
0x14000ba80  mov     rdi, rcx
0x14000ba83  mov     byte ptr [rax+8], 0
0x14000ba87  lea     rcx, [rax+8]; Irql
0x14000ba8b  mov     esi, edx
0x14000ba8d  call    cs:__imp_IoAcquireCancelSpinLock
0x14000ba94  nop     dword ptr [rax+rax+00h]
0x14000ba99  mov     rbx, [rdi+18h]
0x14000ba9d  mov     qword ptr [rdi+18h], 0
0x14000baa5  test    rbx, rbx
0x14000baa8  jz      loc_14000BB87
0x14000baae  mov     rax, [rbx+0B8h]
0x14000bab5  test    rax, rax
0x14000bab8  jz      loc_14000BB87
0x14000babe  cmp     [rax+20h], rdi
0x14000bac2  jnz     loc_14000BB87
0x14000bac8  mov     qword ptr [rax+20h], 0
0x14000bad0  xor     eax, eax
0x14000bad2  xchg    rax, [rbx+68h]
0x14000bad6  mov     cl, [rsp+38h+Irql]; Irql
0x14000bada  call    cs:__imp_IoReleaseCancelSpinLock
0x14000bae1  nop     dword ptr [rax+rax+00h]
0x14000bae6  test    esi, esi
0x14000bae8  jz      short loc_14000BB62
0x14000baea  mov     eax, 0C00000B5h
0x14000baef  mov     [rsp+38h+arg_10], 0
0x14000baf4  mov     [rbx+30h], eax
0x14000baf7  mov     qword ptr [rbx+38h], 0
0x14000baff  cmp     byte ptr cs:xmmword_140038420+2, 0
0x14000bb06  jl      loc_14000BB99
0x14000bb0c  lea     rcx, [rsp+38h+arg_10]; Irql
0x14000bb11  call    cs:__imp_IoAcquireCancelSpinLock
0x14000bb18  nop     dword ptr [rax+rax+00h]
0x14000bb1d  xor     eax, eax
0x14000bb1f  xchg    rax, [rbx+68h]
0x14000bb23  mov     cl, [rsp+38h+arg_10]; Irql
0x14000bb27  call    cs:__imp_IoReleaseCancelSpinLock
0x14000bb2e  nop     dword ptr [rax+rax+00h]
0x14000bb33  mov     dl, 2; PriorityBoost
0x14000bb35  mov     rcx, rbx; Irp
0x14000bb38  call    cs:__imp_IofCompleteRequest
0x14000bb3f  nop     dword ptr [rax+rax+00h]
0x14000bb44  mov     edx, 4
0x14000bb49  mov     rcx, rdi
0x14000bb4c  call    FreeTracker
0x14000bb51  mov     rbx, [rsp+38h+arg_8]
0x14000bb56  mov     rsi, [rsp+38h+arg_18]
0x14000bb5b  add     rsp, 30h
0x14000bb5f  pop     rdi
0x14000bb60  retn
0x14000bb62  mov     r8, rdi
0x14000bb65  mov     rdx, rbx
0x14000bb68  xor     ecx, ecx
0x14000bb6a  call    CopyFindNameData
0x14000bb6f  test    eax, eax
0x14000bb71  js      loc_14000BAEA
0x14000bb77  or      r8d, 0FFFFFFFFh
0x14000bb7b  mov     edx, eax
0x14000bb7d  mov     rcx, rbx; Irp
0x14000bb80  call    NTIoComplete
0x14000bb85  jmp     short loc_14000BB44
0x14000bb87  mov     cl, [rsp+38h+Irql]; Irql
0x14000bb8b  call    cs:__imp_IoReleaseCancelSpinLock
0x14000bb92  nop     dword ptr [rax+rax+00h]
0x14000bb97  jmp     short loc_14000BB44
0x14000bb99  mov     edx, 46h ; 'F'
0x14000bb9e  mov     [rsp+38h+var_10], 0
0x14000bba6  mov     ecx, 417h
0x14000bbab  mov     [rsp+38h+var_18], eax
0x14000bbaf  mov     r9, rbx
0x14000bbb2  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x14000bbb9  call    WPP_SF_qdd
0x14000bbbe  jmp     loc_14000BB0C
```
