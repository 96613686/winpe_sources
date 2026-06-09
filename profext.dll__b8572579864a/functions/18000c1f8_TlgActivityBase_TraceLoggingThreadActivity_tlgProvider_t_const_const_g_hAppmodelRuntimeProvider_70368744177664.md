# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)

- ea: `0x18000c1f8`
- end: `0x18000c246`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hAppmodelRuntimeProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c1ec`
- `0x18000d610`
- `0x18000e270`
- `0x18000e650`
- `0x180015da0`

## callees

- `0x18000c1f8`
- `0x18001317c`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000c222`
- `ntdll!EtwEventActivityIdControl` at `0x18000c222`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hAppmodelRuntimeProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EtwEventActivityIdControl(4, a1 + 24);
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<70368744177664,5>(&dword_180031038, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x18000c1f8  push    rbx
0x18000c1fa  sub     rsp, 20h
0x18000c1fe  cmp     dword ptr [rcx], 1
0x18000c201  mov     rbx, rcx
0x18000c204  jz      short loc_18000C213
0x18000c206  mov     dword ptr [rbx], 3
0x18000c20c  add     rsp, 20h
0x18000c210  pop     rbx
0x18000c211  retn
0x18000c213  cmp     byte ptr [rcx+4], 0
0x18000c217  jz      short loc_18000C22E
0x18000c219  lea     rdx, [rcx+18h]
0x18000c21d  mov     ecx, 4
0x18000c222  call    cs:__imp_EtwEventActivityIdControl
0x18000c229  nop     dword ptr [rax+rax+00h]
0x18000c22e  lea     rdx, [rbx+8]
0x18000c232  mov     dword ptr [rbx], 2
0x18000c238  lea     rcx, dword_180031038
0x18000c23f  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x18000c244  jmp     short loc_18000C206
```
