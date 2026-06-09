# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)

- ea: `0x1800101fc`
- end: `0x180010241`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010160`
- `0x1800126e4`
- `0x18001fe69`
- `0x18002040e`

## callees

- `0x1800080e8`
- `0x1800101fc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010219`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180010219`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<70368744177664,5>((unsigned int *)&dword_180031038);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x1800101fc  push    rbx
0x1800101fe  sub     rsp, 20h
0x180010202  mov     rbx, rcx
0x180010205  cmp     dword ptr [rcx], 1
0x180010208  jnz     short loc_180010235
0x18001020a  cmp     byte ptr [rcx+4], 0
0x18001020e  jz      short loc_18001021F
0x180010210  lea     rdx, [rcx+18h]; ActivityId
0x180010214  mov     ecx, 4; ControlCode
0x180010219  call    cs:__imp_EventActivityIdControl
0x18001021f  mov     dword ptr [rbx], 2
0x180010225  lea     rdx, [rbx+8]
0x180010229  lea     rcx, dword_180031038
0x180010230  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x180010235  mov     dword ptr [rbx], 3
0x18001023b  add     rsp, 20h
0x18001023f  pop     rbx
0x180010240  retn
```
