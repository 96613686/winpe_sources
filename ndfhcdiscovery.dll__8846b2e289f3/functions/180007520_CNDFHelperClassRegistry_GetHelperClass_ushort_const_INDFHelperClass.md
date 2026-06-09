# CNDFHelperClassRegistry::GetHelperClass(ushort const *,INDFHelperClass * *)

- ea: `0x180007520`
- end: `0x1800075b8`
- name: `?GetHelperClass@CNDFHelperClassRegistry@@UEAAJPEBGPEAPEAUINDFHelperClass@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, const unsigned __int16 *, struct INDFHelperClass **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180007520`
- `0x180007a20`
- `0x180008a20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007548`
- `KERNEL32!EnterCriticalSection` at `0x180007548`
- `KERNEL32!LeaveCriticalSection` at `0x18000756e`
- `KERNEL32!LeaveCriticalSection` at `0x18000758b`
- `KERNEL32!LeaveCriticalSection` at `0x18000756e`
- `KERNEL32!LeaveCriticalSection` at `0x18000758b`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::GetHelperClass(
        CNDFHelperClassRegistry *this,
        const unsigned __int16 *a2,
        struct INDFHelperClass **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int v7; // esi

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 656);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 656));
  if ( !*((_DWORD *)this + 158) )
  {
    v7 = CNDFHelperClassRegistry::InitializeData(this);
    if ( v7 < 0 )
    {
      LeaveCriticalSection(v6);
      return (unsigned int)v7;
    }
    *((_DWORD *)this + 158) = 1;
  }
  LeaveCriticalSection(v6);
  return CNDFHelperClassRegistry::PrivGetHelperClass(this, a2, a3);
}

```

## disassembly

```asm
0x180007520  push    rbx
0x180007522  push    rbp
0x180007523  push    rsi
0x180007524  push    rdi
0x180007525  push    r14
0x180007527  sub     rsp, 20h
0x18000752b  mov     rbp, r8
0x18000752e  mov     r14, rdx
0x180007531  mov     rbx, rcx
0x180007534  test    rdx, rdx
0x180007537  jz      short loc_1800075A7
0x180007539  test    r8, r8
0x18000753c  jz      short loc_1800075A7
0x18000753e  lea     rdi, [rcx+290h]
0x180007545  mov     rcx, rdi; lpCriticalSection
0x180007548  call    cs:__imp_EnterCriticalSection
0x18000754f  nop     dword ptr [rax+rax+00h]
0x180007554  cmp     dword ptr [rbx+278h], 0
0x18000755b  jnz     short loc_180007588
0x18000755d  mov     rcx, rbx; this
0x180007560  call    ?InitializeData@CNDFHelperClassRegistry@@AEAAJXZ; CNDFHelperClassRegistry::InitializeData(void)
0x180007565  mov     esi, eax
0x180007567  test    eax, eax
0x180007569  jns     short loc_18000757E
0x18000756b  mov     rcx, rdi; lpCriticalSection
0x18000756e  call    cs:__imp_LeaveCriticalSection
0x180007575  nop     dword ptr [rax+rax+00h]
0x18000757a  mov     eax, esi
0x18000757c  jmp     short loc_1800075AC
0x18000757e  mov     dword ptr [rbx+278h], 1
0x180007588  mov     rcx, rdi; lpCriticalSection
0x18000758b  call    cs:__imp_LeaveCriticalSection
0x180007592  nop     dword ptr [rax+rax+00h]
0x180007597  mov     r8, rbp; struct INDFHelperClass **
0x18000759a  mov     rdx, r14; unsigned __int16 *
0x18000759d  mov     rcx, rbx; this
0x1800075a0  call    ?PrivGetHelperClass@CNDFHelperClassRegistry@@AEAAJPEBGPEAPEAUINDFHelperClass@@@Z; CNDFHelperClassRegistry::PrivGetHelperClass(ushort const *,INDFHelperClass * *)
0x1800075a5  jmp     short loc_1800075AC
0x1800075a7  mov     eax, 80070057h
0x1800075ac  add     rsp, 20h
0x1800075b0  pop     r14
0x1800075b2  pop     rdi
0x1800075b3  pop     rsi
0x1800075b4  pop     rbp
0x1800075b5  pop     rbx
0x1800075b6  retn
```
