# _lambda_c7b5acbfa5fe69ccd764c511e264b77e_::operator()

- ea: `0x180011028`
- end: `0x1800110bc`
- name: `_lambda_c7b5acbfa5fe69ccd764c511e264b77e_::operator()`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800114ac`

## callees

- `0x18000ebc0`
- `0x180011028`
- `0x180013b08`
- `0x18001417c`

## import_xrefs

- `certenroll!__imp_FreeEnrollAIKResult` at `0x1800110b5`

## string_xrefs

- `0x180011095`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
__int64 __fastcall lambda_c7b5acbfa5fe69ccd764c511e264b77e_::operator()(__int64 a1)
{
  signed int v2; // ecx
  int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = **(_DWORD **)a1;
  if ( v2 < 0 || **(_BYTE **)(a1 + 8) )
    LogAndSaveAIKEnrollmentResult(
      v2,
      **(_BYTE **)(a1 + 16),
      **(_BYTE **)(a1 + 24),
      **(_BYTE **)(a1 + 32),
      **(const unsigned __int16 ***)(a1 + 40),
      *(const struct EnrollAIKResult **)(a1 + 48),
      *(struct _RETRYINFO **)(a1 + 56));
  v3 = SetAikTaskTriggers(
         **(_DWORD **)a1,
         *(const struct EnrollAIKResult **)(a1 + 48),
         *(const struct _LLFILETIME **)(a1 + 56));
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4FE,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3);
  return FreeEnrollAIKResult(**(_QWORD **)(a1 + 64));
}

```

## disassembly

```asm
0x180011028  push    rbx
0x18001102a  sub     rsp, 40h
0x18001102e  mov     rax, [rcx]
0x180011031  mov     rbx, rcx
0x180011034  mov     ecx, [rax]; unsigned int
0x180011036  test    ecx, ecx
0x180011038  js      short loc_180011043
0x18001103a  mov     rax, [rbx+8]
0x18001103e  cmp     byte ptr [rax], 0
0x180011041  jz      short loc_18001107A
0x180011043  mov     rax, [rbx+38h]
0x180011047  mov     r10, [rbx+28h]
0x18001104b  mov     r9, [rbx+20h]
0x18001104f  mov     r8, [rbx+18h]
0x180011053  mov     rdx, [rbx+10h]
0x180011057  mov     [rsp+48h+var_18], rax; struct _RETRYINFO *
0x18001105c  mov     rax, [rbx+30h]
0x180011060  mov     r9b, [r9]; bool
0x180011063  mov     r8b, [r8]; bool
0x180011066  mov     dl, [rdx]; bool
0x180011068  mov     [rsp+48h+var_20], rax; struct EnrollAIKResult *
0x18001106d  mov     rax, [r10]
0x180011070  mov     [rsp+48h+var_28], rax; int
0x180011075  call    ?LogAndSaveAIKEnrollmentResult@@YAXJ_N00PEBGPEBUEnrollAIKResult@@PEAU_RETRYINFO@@@Z; LogAndSaveAIKEnrollmentResult(long,bool,bool,bool,ushort const *,EnrollAIKResult const *,_RETRYINFO *)
0x18001107a  mov     rcx, [rbx]
0x18001107d  mov     r8, [rbx+38h]; struct _RETRYINFO *
0x180011081  mov     rdx, [rbx+30h]; struct EnrollAIKResult *
0x180011085  mov     ecx, [rcx]; int
0x180011087  call    ?SetAikTaskTriggers@@YAJJPEBUEnrollAIKResult@@PEBU_RETRYINFO@@@Z; SetAikTaskTriggers(long,EnrollAIKResult const *,_RETRYINFO const *)
0x18001108c  test    eax, eax
0x18001108e  jns     short loc_1800110A9
0x180011090  mov     rcx, [rsp+48h]; this
0x180011095  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001109c  mov     r9d, eax; char *
0x18001109f  mov     edx, 4FEh; void *
0x1800110a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800110a9  mov     rcx, [rbx+40h]
0x1800110ad  mov     rcx, [rcx]
0x1800110b0  add     rsp, 40h
0x1800110b4  pop     rbx
0x1800110b5  jmp     cs:__imp_FreeEnrollAIKResult
```
