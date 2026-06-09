# TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hDiskProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hDiskProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(void)

- ea: `0x1400055a8`
- end: `0x1400055ed`
- name: `??1?$TraceLoggingThreadActivity@$1?g_hDiskProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c917`

## callees

- `0x140005444`
- `0x1400055a8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400055c5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1400055c5`

## pseudocode

```c
__int64 __fastcall TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hDiskProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hDiskProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_BYTE *)(a1 + 4) )
      EventActivityIdControl(4u, (LPGUID)(a1 + 24));
    *(_DWORD *)a1 = 2;
    result = _tlgWriteActivityAutoStop<0,5>((unsigned int *)&dword_140014000, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
  return result;
}

```

## disassembly

```asm
0x1400055a8  push    rbx
0x1400055aa  sub     rsp, 20h
0x1400055ae  cmp     dword ptr [rcx], 1
0x1400055b1  mov     rbx, rcx
0x1400055b4  jnz     short loc_1400055E1
0x1400055b6  cmp     byte ptr [rcx+4], 0
0x1400055ba  jz      short loc_1400055CB
0x1400055bc  lea     rdx, [rcx+18h]; ActivityId
0x1400055c0  mov     ecx, 4; ControlCode
0x1400055c5  call    cs:__imp_EventActivityIdControl
0x1400055cb  lea     rdx, [rbx+8]
0x1400055cf  mov     dword ptr [rbx], 2
0x1400055d5  lea     rcx, dword_140014000
0x1400055dc  call    ??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)
0x1400055e1  mov     dword ptr [rbx], 3
0x1400055e7  add     rsp, 20h
0x1400055eb  pop     rbx
0x1400055ec  retn
```
