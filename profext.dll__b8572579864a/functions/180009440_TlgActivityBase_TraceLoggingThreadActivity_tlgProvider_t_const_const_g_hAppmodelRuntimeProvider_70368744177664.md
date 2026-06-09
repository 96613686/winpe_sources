# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)

- ea: `0x180009440`
- end: `0x1800094c3`
- name: `?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d610`
- `0x18000e270`
- `0x18000e650`
- `0x180015da0`

## callees

- `0x180009440`
- `0x18000ee08`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000947b`
- `ntdll!EtwEventActivityIdControl` at `0x180009498`
- `ntdll!EtwEventActivityIdControl` at `0x18000947b`
- `ntdll!EtwEventActivityIdControl` at `0x180009498`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(
        __int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)dword_180031038;
  if ( (unsigned int)dword_180031038 > 5 && (result = tlgKeywordOn(&dword_180031038, 0x400000000000LL), (_BYTE)result) )
  {
    EtwEventActivityIdControl(3, a1 + 8);
    *(_OWORD *)(a1 + 24) = *(_OWORD *)(a1 + 8);
    result = EtwEventActivityIdControl(4, a1 + 24);
    *(_BYTE *)(a1 + 4) = 1;
  }
  else
  {
    *(_OWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)a1 = 1;
  return result;
}

```

## disassembly

```asm
0x180009440  mov     [rsp+arg_0], rbx
0x180009445  push    rdi
0x180009446  sub     rsp, 20h
0x18000944a  mov     eax, cs:dword_180031038
0x180009450  mov     rdi, rcx
0x180009453  cmp     eax, 5
0x180009456  jbe     short loc_1800094AA
0x180009458  mov     rdx, 400000000000h
0x180009462  lea     rcx, dword_180031038
0x180009469  call    _tlgKeywordOn
0x18000946e  test    al, al
0x180009470  jz      short loc_1800094AA
0x180009472  lea     rdx, [rdi+8]
0x180009476  mov     ecx, 3
0x18000947b  call    cs:__imp_EtwEventActivityIdControl
0x180009482  nop     dword ptr [rax+rax+00h]
0x180009487  movups  xmm0, xmmword ptr [rdi+8]
0x18000948b  lea     rdx, [rdi+18h]
0x18000948f  mov     ecx, 4
0x180009494  movdqu  xmmword ptr [rdx], xmm0
0x180009498  call    cs:__imp_EtwEventActivityIdControl
0x18000949f  nop     dword ptr [rax+rax+00h]
0x1800094a4  mov     byte ptr [rdi+4], 1
0x1800094a8  jmp     short loc_1800094B1
0x1800094aa  xorps   xmm0, xmm0
0x1800094ad  movups  xmmword ptr [rdi+8], xmm0
0x1800094b1  mov     rbx, [rsp+28h+arg_0]
0x1800094b6  mov     dword ptr [rdi], 1
0x1800094bc  add     rsp, 20h
0x1800094c0  pop     rdi
0x1800094c1  retn
```
