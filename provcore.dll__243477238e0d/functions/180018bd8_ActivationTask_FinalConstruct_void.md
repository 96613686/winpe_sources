# ActivationTask::FinalConstruct(void)

- ea: `0x180018bd8`
- end: `0x180018c56`
- name: `?FinalConstruct@ActivationTask@@QEAAJXZ`
- size: `126`
- prototype: `HRESULT __fastcall(ActivationTask *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800185b4`
- `0x1800186a8`

## callees

- `0x180012770`
- `0x180018bd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018bf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c34`

## pseudocode

```c
__int64 __fastcall ActivationTask::FinalConstruct(ActivationTask *this)
{
  unsigned int v1; // edi
  HANDLE EventW; // rax
  signed int LastError; // eax

  v1 = 0;
  this->m_taskThread = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  this->m_cancelEvent = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Eu, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids, 0);
    }
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x180018bd8  mov     [rsp+arg_0], rbx
0x180018bdd  push    rdi
0x180018bde  sub     rsp, 20h
0x180018be2  xor     edi, edi
0x180018be4  mov     rbx, this
0x180018be7  mov     [this+48h], rdi
0x180018beb  xor     r9d, r9d; lpName
0x180018bee  xor     r8d, r8d; bInitialState
0x180018bf1  xor     ecx, ecx; lpEventAttributes
0x180018bf3  lea     edx, [rdi+1]; bManualReset
0x180018bf6  call    cs:__imp_CreateEventW
0x180018bfc  mov     [rbx+40h], rax
0x180018c00  test    rax, rax
0x180018c03  jnz     short loc_180018C49
0x180018c05  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180018c0c  lea     rax, WPP_GLOBAL_Control
0x180018c13  cmp     this, rax
0x180018c16  jz      short loc_180018C34
0x180018c18  test    byte ptr [this+1Ch], 2
0x180018c1c  jz      short loc_180018C34
0x180018c1e  mov     this, [this+10h]; Logger
0x180018c22  lea     edx, [rdi+2Eh]; id
0x180018c25  xor     r9d, r9d; _a1
0x180018c28  lea     r8, WPP_134a5cb9373134b19d236cc06387f3ce_Traceguids; TraceGuid
0x180018c2f  call    WPP_SF_d
0x180018c34  call    cs:__imp_GetLastError
0x180018c3a  mov     edi, eax
0x180018c3c  test    eax, eax
0x180018c3e  jle     short loc_180018C49
0x180018c40  movzx   edi, ax
0x180018c43  or      edi, 80070000h
0x180018c49  mov     rbx, [rsp+28h+arg_0]
0x180018c4e  mov     eax, edi
0x180018c50  add     rsp, 20h
0x180018c54  pop     rdi
0x180018c55  retn
```
