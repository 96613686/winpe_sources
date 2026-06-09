# CTouchSelectionHandle::InitICM(void)

- ea: `0x180201370`
- end: `0x180201465`
- name: `?InitICM@CTouchSelectionHandle@@UEAAJXZ`
- size: `245`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18013ce80`
- `0x180201370`

## import_xrefs

- `NInput!CreateInteractionContext` at `0x180201393`
- `NInput!CreateInteractionContext` at `0x180201393`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1802013b4`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x1802013b4`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1802013f1`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1802013f1`
- `NInput!SetPropertyInteractionContext` at `0x18020140e`
- `NInput!SetPropertyInteractionContext` at `0x180201427`
- `NInput!SetPropertyInteractionContext` at `0x180201440`
- `NInput!SetPropertyInteractionContext` at `0x18020140e`
- `NInput!SetPropertyInteractionContext` at `0x180201427`
- `NInput!SetPropertyInteractionContext` at `0x180201440`

## pseudocode

```c
__int64 __fastcall CTouchSelectionHandle::InitICM(CTouchSelectionHandle *this)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  __int64 v4; // rcx
  _OWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (_QWORD *)((char *)this + 8);
  result = CreateInteractionContext((char *)this + 8);
  if ( (int)result >= 0 )
  {
    result = RegisterOutputCallbackInteractionContext(*v1, CTouchTracker::OutputCallback, this);
    if ( (int)result >= 0 )
    {
      v4 = *v1;
      v5[0] = _mm_load_si128((const __m128i *)&_xmm);
      v5[1] = _mm_load_si128((const __m128i *)&_xmm);
      result = SetInteractionConfigurationInteractionContext(v4, 4, v5);
      if ( (int)result >= 0 )
      {
        result = SetPropertyInteractionContext(*v1, 1, 1);
        if ( (int)result >= 0 )
        {
          result = SetPropertyInteractionContext(*v1, 2, 1);
          if ( (int)result >= 0 )
            return SetPropertyInteractionContext(*v1, 3, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180201370  mov     [rsp+arg_8], rbx
0x180201375  push    rdi
0x180201376  sub     rsp, 50h
0x18020137a  mov     rax, cs:__security_cookie
0x180201381  xor     rax, rsp
0x180201384  mov     [rsp+58h+var_18], rax
0x180201389  lea     rbx, [rcx+8]
0x18020138d  mov     rdi, rcx
0x180201390  mov     rcx, rbx
0x180201393  call    cs:__imp_CreateInteractionContext
0x18020139a  nop     dword ptr [rax+rax+00h]
0x18020139f  test    eax, eax
0x1802013a1  js      loc_18020144C
0x1802013a7  mov     rcx, [rbx]
0x1802013aa  lea     rdx, ?OutputCallback@CTouchTracker@@KAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CTouchTracker::OutputCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x1802013b1  mov     r8, rdi
0x1802013b4  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x1802013bb  nop     dword ptr [rax+rax+00h]
0x1802013c0  test    eax, eax
0x1802013c2  js      loc_18020144C
0x1802013c8  movdqa  xmm0, cs:__xmm@00000001000000030000000100000002
0x1802013d0  lea     r8, [rsp+58h+var_38]
0x1802013d5  movdqa  xmm1, cs:__xmm@00000007000000010000000100000004
0x1802013dd  mov     edx, 4
0x1802013e2  mov     rcx, [rbx]
0x1802013e5  movdqu  [rsp+58h+var_38], xmm0
0x1802013eb  movdqu  [rsp+58h+var_28], xmm1
0x1802013f1  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1802013f8  nop     dword ptr [rax+rax+00h]
0x1802013fd  test    eax, eax
0x1802013ff  js      short loc_18020144C
0x180201401  mov     rcx, [rbx]
0x180201404  mov     edi, 1
0x180201409  mov     r8d, edi
0x18020140c  mov     edx, edi
0x18020140e  call    cs:__imp_SetPropertyInteractionContext
0x180201415  nop     dword ptr [rax+rax+00h]
0x18020141a  test    eax, eax
0x18020141c  js      short loc_18020144C
0x18020141e  mov     rcx, [rbx]
0x180201421  lea     edx, [rdi+1]
0x180201424  mov     r8d, edi
0x180201427  call    cs:__imp_SetPropertyInteractionContext
0x18020142e  nop     dword ptr [rax+rax+00h]
0x180201433  test    eax, eax
0x180201435  js      short loc_18020144C
0x180201437  mov     rcx, [rbx]
0x18020143a  lea     edx, [rdi+2]
0x18020143d  xor     r8d, r8d
0x180201440  call    cs:__imp_SetPropertyInteractionContext
0x180201447  nop     dword ptr [rax+rax+00h]
0x18020144c  mov     rcx, [rsp+58h+var_18]
0x180201451  xor     rcx, rsp; StackCookie
0x180201454  call    __security_check_cookie
0x180201459  mov     rbx, [rsp+58h+arg_8]
0x18020145e  add     rsp, 50h
0x180201462  pop     rdi
0x180201463  retn
```
