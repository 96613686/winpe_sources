# CDimsJobTaskHandler::~CDimsJobTaskHandler(void)

- ea: `0x1800022f0`
- end: `0x180002372`
- name: `??1CDimsJobTaskHandler@@IEAA@XZ`
- size: `130`
- prototype: `void __fastcall(CDimsJobTaskHandler *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800020f0`
- `0x180002270`

## callees

- `0x1800022f0`
- `0x180002380`
- `0x18000a338`
- `0x18000aac8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000233b`

## pseudocode

```c
void __fastcall CDimsJobTaskHandler::~CDimsJobTaskHandler(CDimsJobTaskHandler *this)
{
  CDims *v2; // rbx

  *(_QWORD *)this = &CDimsJobTaskHandler::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids);
  if ( *((_DWORD *)this + 14) > 3u )
    LogReport(DM_LOG_INFO_STOPPED, 0, 0);
  v2 = (CDims *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    CDims::~CDims(v2);
    LocalFree(v2);
  }
}

```

## disassembly

```asm
0x1800022f0  push    rbx
0x1800022f2  sub     rsp, 20h
0x1800022f6  mov     rbx, rcx
0x1800022f9  lea     rax, ??_7CDimsJobTaskHandler@@6B@; const CDimsJobTaskHandler::`vftable'
0x180002300  mov     [rcx], rax
0x180002303  lea     rax, WPP_GLOBAL_Control
0x18000230a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002311  cmp     rcx, rax
0x180002314  jz      short loc_18000231C
0x180002316  test    byte ptr [rcx+1Ch], 10h
0x18000231a  jnz     short loc_180002348
0x18000231c  cmp     dword ptr [rbx+38h], 3
0x180002320  ja      short loc_18000235F
0x180002322  mov     rbx, [rbx+30h]
0x180002326  test    rbx, rbx
0x180002329  jz      short loc_180002342
0x18000232b  mov     rcx, rbx; this
0x18000232e  call    ??1CDims@@QEAA@XZ; CDims::~CDims(void)
0x180002333  mov     rcx, rbx
0x180002336  add     rsp, 20h
0x18000233a  pop     rbx
0x18000233b  jmp     cs:__imp_LocalFree
0x180002342  add     rsp, 20h
0x180002346  pop     rbx
0x180002347  retn
0x180002348  mov     edx, 0Bh
0x18000234d  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x180002354  mov     rcx, [rcx+10h]
0x180002358  call    WPP_SF_
0x18000235d  jmp     short loc_18000231C
0x18000235f  xor     r8d, r8d
0x180002362  xor     edx, edx
0x180002364  lea     rcx, DM_LOG_INFO_STOPPED
0x18000236b  call    _LogReport
0x180002370  jmp     short loc_180002322
```
