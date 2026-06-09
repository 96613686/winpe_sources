# CASFOutput::ConnectionMediaType(_AMMediaType *)

- ea: `0x180009020`
- end: `0x1800090e7`
- name: `?ConnectionMediaType@CASFOutput@@UEAAJPEAU_AMMediaType@@@Z`
- size: `199`
- prototype: `int(CASFOutput *__hidden this, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001cfc`
- `0x180007104`
- `0x180009020`
- `0x180016314`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000904b`
- `KERNEL32!EnterCriticalSection` at `0x18000904b`
- `KERNEL32!LeaveCriticalSection` at `0x180009082`
- `KERNEL32!LeaveCriticalSection` at `0x1800090a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800090cc`
- `KERNEL32!LeaveCriticalSection` at `0x180009082`
- `KERNEL32!LeaveCriticalSection` at `0x1800090a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800090cc`
- `ole32!CoTaskMemFree` at `0x18000909d`
- `ole32!CoTaskMemFree` at `0x18000909d`

## pseudocode

```c
__int64 __fastcall CASFOutput::ConnectionMediaType(CASFOutput *this, struct _AMMediaType *a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  const struct _AMMediaType *v6; // rax
  struct _AMMediaType *v7; // rsi

  if ( !a2 )
    return 2147500035LL;
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 5);
  EnterCriticalSection(v5);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_DWORD *)this + 77) )
    {
      v6 = ConstructVIH1Type((const struct _AMMediaType *)((char *)this + 80));
      v7 = (struct _AMMediaType *)v6;
      if ( !v6 )
      {
        LeaveCriticalSection(v5);
        return 2147942414LL;
      }
      CopyMediaType(a2, v6);
      CoTaskMemFree(v7);
    }
    else
    {
      CopyMediaType(a2, (const struct _AMMediaType *)((char *)this + 80));
    }
    LeaveCriticalSection(v5);
    return 0;
  }
  else
  {
    memset_0(a2, 0, sizeof(struct _AMMediaType));
    a2->lSampleSize = 1;
    a2->bFixedSizeSamples = 1;
    LeaveCriticalSection(v5);
    return 2147746313LL;
  }
}

```

## disassembly

```asm
0x180009020  mov     [rsp+arg_0], rbx
0x180009025  mov     [rsp+arg_8], rsi
0x18000902a  push    rdi
0x18000902b  sub     rsp, 20h
0x18000902f  mov     rbx, rdx
0x180009032  mov     rsi, rcx
0x180009035  test    rdx, rdx
0x180009038  jnz     short loc_180009044
0x18000903a  mov     eax, 80004003h
0x18000903f  jmp     loc_1800090D7
0x180009044  mov     rdi, [rcx+28h]
0x180009048  mov     rcx, rdi; lpCriticalSection
0x18000904b  call    cs:__imp_EnterCriticalSection
0x180009051  cmp     qword ptr [rsi+18h], 0
0x180009056  jz      short loc_1800090B0
0x180009058  cmp     dword ptr [rsi+134h], 0
0x18000905f  lea     rcx, [rsi+50h]; struct _AMMediaType *
0x180009063  jnz     short loc_180009072
0x180009065  mov     rdx, rcx; struct _AMMediaType *
0x180009068  mov     rcx, rbx; struct _AMMediaType *
0x18000906b  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180009070  jmp     short loc_1800090A3
0x180009072  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x180009077  mov     rsi, rax
0x18000907a  test    rax, rax
0x18000907d  jnz     short loc_18000908F
0x18000907f  mov     rcx, rdi; lpCriticalSection
0x180009082  call    cs:__imp_LeaveCriticalSection
0x180009088  mov     eax, 8007000Eh
0x18000908d  jmp     short loc_1800090D7
0x18000908f  mov     rdx, rsi; struct _AMMediaType *
0x180009092  mov     rcx, rbx; struct _AMMediaType *
0x180009095  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x18000909a  mov     rcx, rsi; pv
0x18000909d  call    cs:__imp_CoTaskMemFree
0x1800090a3  mov     rcx, rdi; lpCriticalSection
0x1800090a6  call    cs:__imp_LeaveCriticalSection
0x1800090ac  xor     eax, eax
0x1800090ae  jmp     short loc_1800090D7
0x1800090b0  xor     edx, edx; Val
0x1800090b2  mov     rcx, rbx; void *
0x1800090b5  lea     r8d, [rdx+58h]; Size
0x1800090b9  call    memset_0
0x1800090be  mov     eax, 1
0x1800090c3  mov     rcx, rdi; lpCriticalSection
0x1800090c6  mov     [rbx+28h], eax
0x1800090c9  mov     [rbx+20h], eax
0x1800090cc  call    cs:__imp_LeaveCriticalSection
0x1800090d2  mov     eax, 80040209h
0x1800090d7  mov     rbx, [rsp+28h+arg_0]
0x1800090dc  mov     rsi, [rsp+28h+arg_8]
0x1800090e1  add     rsp, 20h
0x1800090e5  pop     rdi
0x1800090e6  retn
```
