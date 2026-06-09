# NcaDAPEvidenceUserSnapshotFind

- ea: `0x180003540`
- end: `0x18000360a`
- name: `NcaDAPEvidenceUserSnapshotFind`
- size: `202`
- prototype: `struct NCA_DAP_USER_EVSNPSHT_ *__fastcall(int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008774`
- `0x180009998`
- `0x180015f20`
- `0x180016468`
- `0x180016798`

## callees

- `0x180003540`
- `0x180004f04`
- `0x180015e04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003586`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003586`

## pseudocode

```c
struct NCA_DAP_USER_EVSNPSHT_ *__fastcall NcaDAPEvidenceUserSnapshotFind(int a1)
{
  struct NCA_DAP_USER_EVSNPSHT_ *i; // rcx
  struct NCA_DAP_USER_EVSNPSHT_ *v3; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_618387925699392817eae358b6323a44_Traceguids);
  EnterCriticalSection(&gNcaDapEvSnpshot);
  for ( i = qword_180029528; ; i = *(struct NCA_DAP_USER_EVSNPSHT_ **)i )
  {
    v3 = 0;
    if ( i == (struct NCA_DAP_USER_EVSNPSHT_ *)&qword_180029528 )
      break;
    v3 = i;
    if ( *((_DWORD *)i + 153) == a1 )
    {
      NcaDAPEvidenceUserSnapshotAddRef(i);
      break;
    }
  }
  LeaveCriticalSection(&gNcaDapEvSnpshot);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_618387925699392817eae358b6323a44_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_0], rbx
0x180003545  mov     [rsp+arg_8], rsi
0x18000354a  push    rdi
0x18000354b  sub     rsp, 20h
0x18000354f  mov     edi, ecx
0x180003551  mov     rcx, cs:WPP_GLOBAL_Control
0x180003558  lea     rsi, WPP_GLOBAL_Control
0x18000355f  cmp     rcx, rsi
0x180003562  jz      short loc_18000357F
0x180003564  test    byte ptr [rcx+1Ch], 8
0x180003568  jz      short loc_18000357F
0x18000356a  mov     rcx, [rcx+10h]
0x18000356e  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180003575  mov     edx, 13h
0x18000357a  call    WPP_SF_
0x18000357f  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x180003586  call    cs:__imp_EnterCriticalSection
0x18000358d  nop     dword ptr [rax+rax+00h]
0x180003592  mov     rcx, cs:qword_180029528; struct NCA_DAP_USER_EVSNPSHT_ *
0x180003599  lea     rax, qword_180029528
0x1800035a0  xor     ebx, ebx
0x1800035a2  cmp     rcx, rax
0x1800035a5  jz      short loc_1800035BC
0x1800035a7  mov     rbx, rcx
0x1800035aa  cmp     [rcx+264h], edi
0x1800035b0  jz      short loc_1800035B7
0x1800035b2  mov     rcx, [rcx]
0x1800035b5  jmp     short loc_1800035A0
0x1800035b7  call    ?NcaDAPEvidenceUserSnapshotAddRef@@YAXPEAUNCA_DAP_USER_EVSNPSHT_@@@Z; NcaDAPEvidenceUserSnapshotAddRef(NCA_DAP_USER_EVSNPSHT_ *)
0x1800035bc  lea     rcx, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; lpCriticalSection
0x1800035c3  call    cs:__imp_LeaveCriticalSection
0x1800035ca  nop     dword ptr [rax+rax+00h]
0x1800035cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035d6  cmp     rcx, rsi
0x1800035d9  jz      short loc_1800035F6
0x1800035db  test    byte ptr [rcx+1Ch], 8
0x1800035df  jz      short loc_1800035F6
0x1800035e1  mov     rcx, [rcx+10h]
0x1800035e5  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x1800035ec  mov     edx, 14h
0x1800035f1  call    WPP_SF_
0x1800035f6  mov     rsi, [rsp+28h+arg_8]
0x1800035fb  mov     rax, rbx
0x1800035fe  mov     rbx, [rsp+28h+arg_0]
0x180003603  add     rsp, 20h
0x180003607  pop     rdi
0x180003608  retn
```
