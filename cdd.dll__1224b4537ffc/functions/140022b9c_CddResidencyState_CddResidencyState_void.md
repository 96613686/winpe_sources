# CddResidencyState::~CddResidencyState(void)

- ea: `0x140022b9c`
- end: `0x140022c21`
- name: `??1CddResidencyState@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CddResidencyState *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400015e0`
- `0x14002799c`
- `0x140030f74`
- `0x140032000`

## callees

- `0x140022b9c`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140022bc0`
- `ntoskrnl!DbgPrint` at `0x140022bc0`
- `ntoskrnl!KdDebuggerEnabled` at `0x140022bae`
- `watchdog!WdLogNewEntry5_WdError` at `0x140022be7`
- `watchdog!WdLogNewEntry5_WdError` at `0x140022be7`
- `watchdog!WdLogSingleEntry0` at `0x140022bd1`
- `watchdog!WdLogSingleEntry0` at `0x140022bd1`

## pseudocode

```c
void __fastcall CddResidencyState::~CddResidencyState(CddResidencyState *this)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  _QWORD *v3; // rax

  if ( *((_QWORD *)this + 5) || *((_QWORD *)this + 4) )
  {
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Bitmap is in the LDU list");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1331;
      v3 = (_QWORD *)WdLogNewEntry5_WdError(v2, v1);
      v3[3] = gCddImageInfo;
      v3[4] = (unsigned int)dword_14003E570;
      v3[5] = 215857758;
      WdLogGlobalForLineNumber = 1331;
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x140022b9c  sub     rsp, 28h
0x140022ba0  xor     edx, edx
0x140022ba2  cmp     [rcx+28h], rdx
0x140022ba6  jnz     short loc_140022BAE
0x140022ba8  cmp     [rcx+20h], rdx
0x140022bac  jz      short loc_140022C1B
0x140022bae  mov     rax, cs:KdDebuggerEnabled
0x140022bb5  cmp     [rax], dl
0x140022bb7  jz      short loc_140022C1B
0x140022bb9  lea     rcx, aBitmapIsInTheL; "Bitmap is in the LDU list"
0x140022bc0  call    cs:__imp_DbgPrint
0x140022bc7  nop     dword ptr [rax+rax+00h]
0x140022bcc  mov     ecx, 2
0x140022bd1  call    cs:__imp_WdLogSingleEntry0
0x140022bd8  nop     dword ptr [rax+rax+00h]
0x140022bdd  mov     cs:WdLogGlobalForLineNumber, 533h
0x140022be7  call    cs:__imp_WdLogNewEntry5_WdError
0x140022bee  nop     dword ptr [rax+rax+00h]
0x140022bf3  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022bfa  mov     [rax+18h], rcx
0x140022bfe  mov     ecx, cs:dword_14003E570
0x140022c04  mov     [rax+20h], rcx
0x140022c08  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022c10  mov     cs:WdLogGlobalForLineNumber, 533h
0x140022c1a  int     3; Trap to Debugger
0x140022c1b  add     rsp, 28h
0x140022c1f  retn
```
