# CDwmAppHost::StartComposition(void)

- ea: `0x140004470`
- end: `0x140004543`
- name: `?StartComposition@CDwmAppHost@@AEAAJXZ`
- size: `211`
- prototype: `__int64 __fastcall(CDwmAppHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003480`

## callees

- `0x1400023dc`
- `0x140002e6c`
- `0x140004470`
- `0x14000ce0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400044c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400044c3`
- `api-ms-win-composition-windowmanager-l1-1-0!__imp_DwmClientStartup` at `0x1400044e7`
- `api-ms-win-composition-windowmanager-l1-1-0!__imp_DwmClientStartup` at `0x1400044e7`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTSetProcessSchedulingPriorityClass` at `0x1400044d1`
- `api-ms-win-dx-d3dkmt-l1-1-0!D3DKMTSetProcessSchedulingPriorityClass` at `0x1400044d1`
- `dwmcore!MilCompositionEngine_Initialize` at `0x140004496`
- `dwmcore!MilCompositionEngine_Initialize` at `0x140004496`

## pseudocode

```c
__int64 __fastcall CDwmAppHost::StartComposition(CDwmAppHost *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  HANDLE CurrentProcess; // rax
  CDwmAppHost *v4; // rcx
  int v5; // eax
  int started; // eax
  struct HMIL_CONNECTION__ *v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = this;
  if ( dword_14001C068 || (v8 = 0, v1 = MilCompositionEngine_Initialize(15, &v8), v2 = v1, v1 >= 0) )
  {
    if ( (Microsoft_Windows_Dwm_DwmEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer();
    CurrentProcess = GetCurrentProcess();
    D3DKMTSetProcessSchedulingPriorityClass(CurrentProcess, 5);
    if ( dword_14001C068 || (v5 = DwmClientStartup(&g_dwmAppHost), v2 = v5, v5 >= 0) )
    {
      started = CDwmAppHost::StartKernelRedirection(v4);
      v2 = started;
      if ( started < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, started, 0x14Bu, 0);
      else
        byte_14001C0E8 = 1;
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v5, 0x148u, 0);
    }
  }
  else
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, 0x13Du, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x140004470  mov     [rsp+arg_0], rcx
0x140004475  push    rbx
0x140004476  sub     rsp, 30h
0x14000447a  cmp     cs:dword_14001C068, 0
0x140004481  jnz     short loc_1400044B5
0x140004483  lea     rdx, [rsp+38h+arg_0]
0x140004488  mov     [rsp+38h+arg_0], 0
0x140004491  mov     ecx, 0Fh
0x140004496  call    cs:__imp_?MilCompositionEngine_Initialize@@YAJHPEAPEAUHMIL_CONNECTION__@@@Z; MilCompositionEngine_Initialize(int,HMIL_CONNECTION__ * *)
0x14000449c  mov     ebx, eax
0x14000449e  test    eax, eax
0x1400044a0  jns     short loc_1400044B5
0x1400044a2  mov     [rsp+38h+var_10], 0
0x1400044ab  mov     [rsp+38h+var_18], 13Dh
0x1400044b3  jmp     short loc_14000452B
0x1400044b5  test    cs:Microsoft_Windows_Dwm_DwmEnableBits, 1
0x1400044bc  jz      short loc_1400044C3
0x1400044be  call    McTemplateU0q_EtwEventWriteTransfer
0x1400044c3  call    cs:__imp_GetCurrentProcess
0x1400044c9  mov     rcx, rax
0x1400044cc  mov     edx, 5
0x1400044d1  call    cs:__imp_D3DKMTSetProcessSchedulingPriorityClass
0x1400044d7  cmp     cs:dword_14001C068, 0
0x1400044de  jnz     short loc_140004506
0x1400044e0  lea     rcx, ?g_dwmAppHost@@3VCDwmAppHost@@A; CDwmAppHost g_dwmAppHost
0x1400044e7  call    cs:__imp_DwmClientStartup
0x1400044ed  mov     ebx, eax
0x1400044ef  test    eax, eax
0x1400044f1  jns     short loc_140004506
0x1400044f3  mov     [rsp+38h+var_10], 0
0x1400044fc  mov     [rsp+38h+var_18], 148h
0x140004504  jmp     short loc_14000452B
0x140004506  call    ?StartKernelRedirection@CDwmAppHost@@AEAAJXZ; CDwmAppHost::StartKernelRedirection(void)
0x14000450b  mov     ebx, eax
0x14000450d  test    eax, eax
0x14000450f  js      short loc_14000451A
0x140004511  mov     cs:byte_14001C0E8, 1
0x140004518  jmp     short loc_14000453B
0x14000451a  mov     [rsp+38h+var_10], 0; void *
0x140004523  mov     [rsp+38h+var_18], 14Bh; unsigned int
0x14000452b  xor     edx, edx; int *
0x14000452d  mov     r9d, eax; int
0x140004530  xor     r8d, r8d; unsigned int
0x140004533  lea     ecx, [rdx+14h]; unsigned int
0x140004536  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x14000453b  mov     eax, ebx
0x14000453d  add     rsp, 30h
0x140004541  pop     rbx
0x140004542  retn
```
