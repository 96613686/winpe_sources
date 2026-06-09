# _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)

- ea: `0x1800101b0`
- end: `0x1800101f5`
- name: `??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010148`
- `0x1800126e4`
- `0x18001fe57`
- `0x1800203fc`

## callees

- `0x18000ff74`
- `0x1800101b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800101cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800101cd`

## pseudocode

```c
__int64 __fastcall _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<0,5>((unsigned int *)&dword_180031038, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x1800101b0  push    rbx
0x1800101b2  sub     rsp, 20h
0x1800101b6  mov     rbx, rcx
0x1800101b9  cmp     dword ptr [rcx], 1
0x1800101bc  jnz     short loc_1800101E9
0x1800101be  cmp     byte ptr [rcx+4], 0
0x1800101c2  jz      short loc_1800101D3
0x1800101c4  lea     rdx, [rcx+18h]; ActivityId
0x1800101c8  mov     ecx, 4; ControlCode
0x1800101cd  call    cs:__imp_EventActivityIdControl
0x1800101d3  mov     dword ptr [rbx], 2
0x1800101d9  lea     rdx, [rbx+8]
0x1800101dd  lea     rcx, dword_180031038
0x1800101e4  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x1800101e9  mov     dword ptr [rbx], 3
0x1800101ef  add     rsp, 20h
0x1800101f3  pop     rbx
0x1800101f4  retn
```
