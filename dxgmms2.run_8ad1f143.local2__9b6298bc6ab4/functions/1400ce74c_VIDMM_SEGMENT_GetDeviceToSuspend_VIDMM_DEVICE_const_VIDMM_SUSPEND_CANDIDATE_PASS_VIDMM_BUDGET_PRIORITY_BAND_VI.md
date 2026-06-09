# VIDMM_SEGMENT::GetDeviceToSuspend(VIDMM_DEVICE const *,VIDMM_SUSPEND_CANDIDATE_PASS,VIDMM_BUDGET_PRIORITY_BAND,VIDMM_DEVICE * *)

- ea: `0x1400ce74c`
- end: `0x1400ce8a4`
- name: `?GetDeviceToSuspend@VIDMM_SEGMENT@@QEAAPEAVVIDMM_DEVICE@@PEBV2@W4VIDMM_SUSPEND_CANDIDATE_PASS@@W4VIDMM_BUDGET_PRIORITY_BAND@@PEAPEAV2@@Z`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14010d434`

## callees

- `0x1400ce74c`
- `0x1401103ac`
- `0x140113b48`
- `0x1401153c0`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x1400ce796`
- `ntoskrnl!PsIsSystemProcess` at `0x1400ce796`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ce807`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ce836`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ce807`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ce836`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400ce7fb`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400ce82a`

## pseudocode

```c
VIDMM_DEVICE *__fastcall VIDMM_SEGMENT::GetDeviceToSuspend(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        struct VIDMM_DEVICE **a5)
{
  _QWORD *v5; // rsi
  _QWORD *v6; // r14
  _QWORD *v8; // rdi
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r9
  _QWORD *i; // rdi
  _QWORD *v13; // r12
  VIDMM_DEVICE *v14; // rdi
  __int64 v15; // rdx
  VIDMM_DEVICE *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  VIDMM_DEVICE *result; // rax

  v5 = (_QWORD *)(a1 + 112);
  v6 = *(_QWORD **)(a1 + 112);
  while ( v6 != v5 )
  {
    v8 = v6 - 3;
    v9 = v6;
    v10 = *(v6 - 3);
    v6 = (_QWORD *)*v6;
    if ( !(unsigned __int8)PsIsSystemProcess(*(_QWORD *)(v10 + 16))
      && (*(_BYTE *)(*(_QWORD *)(*v8 + 72LL) + 408LL) & 1) == 0 )
    {
      for ( i = (_QWORD *)v9[2]; i != v9 + 2; i = v13 )
      {
        v13 = (_QWORD *)*i;
        LOBYTE(v11) = a4;
        v14 = (VIDMM_DEVICE *)i[4];
        if ( (unsigned __int8)VIDMM_DEVICE::CanSuspendThisDevice(v14, a2, a3, v11) )
        {
          if ( !VIDMM_DEVICE::IsResumedRecently(v14) )
          {
            if ( g_IsInternalReleaseOrDbg )
            {
              *(_QWORD *)(WdLogNewEntry5_WdTrace(v16, v15) + 24) = v14;
              WdLogGlobalForLineNumber = 6646;
            }
            v19 = *v9;
            if ( *(_QWORD **)(*v9 + 8LL) != v9
              || (v20 = (_QWORD *)v9[1], (_QWORD *)*v20 != v9)
              || (*v20 = v19, *(_QWORD *)(v19 + 8) = v20, v21 = (_QWORD *)v5[1], (_QWORD *)*v21 != v5) )
            {
              __fastfail(3u);
            }
            v9[1] = v21;
            *v9 = v5;
            *v21 = v9;
            result = v14;
            v5[1] = v9;
            return result;
          }
          if ( VIDMM_DEVICE::IsBetterYieldCandidate(v16, *a5) )
          {
            if ( g_IsInternalReleaseOrDbg )
            {
              *(_QWORD *)(WdLogNewEntry5_WdTrace(v18, v17) + 24) = v14;
              WdLogGlobalForLineNumber = 6662;
            }
            *a5 = v14;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400ce74c  mov     [rsp+arg_0], rbx
0x1400ce751  mov     [rsp+arg_10], r8d
0x1400ce756  mov     [rsp+arg_8], rdx
0x1400ce75b  push    rbp
0x1400ce75c  push    rsi
0x1400ce75d  push    rdi
0x1400ce75e  push    r12
0x1400ce760  push    r13
0x1400ce762  push    r14
0x1400ce764  push    r15
0x1400ce766  sub     rsp, 20h
0x1400ce76a  mov     rbp, [rsp+58h+arg_20]
0x1400ce772  lea     rsi, [rcx+70h]
0x1400ce776  mov     r14, [rsi]
0x1400ce779  mov     r13b, r9b
0x1400ce77c  cmp     r14, rsi
0x1400ce77f  jz      loc_1400CE88C
0x1400ce785  lea     rdi, [r14-18h]
0x1400ce789  mov     rbx, r14
0x1400ce78c  mov     rcx, [rdi]
0x1400ce78f  mov     r14, [r14]
0x1400ce792  mov     rcx, [rcx+10h]
0x1400ce796  call    cs:__imp_PsIsSystemProcess
0x1400ce79d  nop     dword ptr [rax+rax+00h]
0x1400ce7a2  test    al, al
0x1400ce7a4  jnz     short loc_1400CE77C
0x1400ce7a6  mov     rax, [rdi]
0x1400ce7a9  mov     rcx, [rax+48h]
0x1400ce7ad  test    byte ptr [rcx+198h], 1
0x1400ce7b4  jnz     short loc_1400CE77C
0x1400ce7b6  lea     r15, [rbx+10h]
0x1400ce7ba  mov     rdi, [r15]
0x1400ce7bd  cmp     rdi, r15
0x1400ce7c0  jz      short loc_1400CE77C
0x1400ce7c2  mov     r12, [rdi]
0x1400ce7c5  mov     r9b, r13b
0x1400ce7c8  mov     rdi, [rdi+20h]
0x1400ce7cc  mov     r8d, [rsp+58h+arg_10]
0x1400ce7d1  mov     rcx, rdi
0x1400ce7d4  mov     rdx, [rsp+58h+arg_8]
0x1400ce7d9  call    ?CanSuspendThisDevice@VIDMM_DEVICE@@QEAA_NPEBV1@W4VIDMM_SUSPEND_CANDIDATE_PASS@@W4VIDMM_BUDGET_PRIORITY_BAND@@@Z; VIDMM_DEVICE::CanSuspendThisDevice(VIDMM_DEVICE const *,VIDMM_SUSPEND_CANDIDATE_PASS,VIDMM_BUDGET_PRIORITY_BAND)
0x1400ce7de  test    al, al
0x1400ce7e0  jz      short loc_1400CE825
0x1400ce7e2  mov     rcx, rdi; this
0x1400ce7e5  call    ?IsResumedRecently@VIDMM_DEVICE@@QEBA_NXZ; VIDMM_DEVICE::IsResumedRecently(void)
0x1400ce7ea  test    al, al
0x1400ce7ec  jz      short loc_1400CE82A
0x1400ce7ee  mov     rdx, [rbp+0]; struct VIDMM_DEVICE *
0x1400ce7f2  call    ?IsBetterYieldCandidate@VIDMM_DEVICE@@QEAA_NPEAV1@@Z; VIDMM_DEVICE::IsBetterYieldCandidate(VIDMM_DEVICE *)
0x1400ce7f7  test    al, al
0x1400ce7f9  jz      short loc_1400CE825
0x1400ce7fb  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400ce802  cmp     byte ptr [rax], 0
0x1400ce805  jz      short loc_1400CE821
0x1400ce807  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400ce80e  nop     dword ptr [rax+rax+00h]
0x1400ce813  mov     [rax+18h], rdi
0x1400ce817  mov     cs:WdLogGlobalForLineNumber, 1A06h
0x1400ce821  mov     [rbp+0], rdi
0x1400ce825  mov     rdi, r12
0x1400ce828  jmp     short loc_1400CE7BD
0x1400ce82a  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400ce831  cmp     byte ptr [rax], 0
0x1400ce834  jz      short loc_1400CE850
0x1400ce836  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400ce83d  nop     dword ptr [rax+rax+00h]
0x1400ce842  mov     [rax+18h], rdi
0x1400ce846  mov     cs:WdLogGlobalForLineNumber, 19F6h
0x1400ce850  mov     rax, [rbx]
0x1400ce853  cmp     [rax+8], rbx
0x1400ce857  jnz     short loc_1400CE885
0x1400ce859  mov     rcx, [rbx+8]
0x1400ce85d  cmp     [rcx], rbx
0x1400ce860  jnz     short loc_1400CE885
0x1400ce862  mov     [rcx], rax
0x1400ce865  mov     [rax+8], rcx
0x1400ce869  mov     rax, [rsi+8]
0x1400ce86d  cmp     [rax], rsi
0x1400ce870  jnz     short loc_1400CE885
0x1400ce872  mov     [rbx+8], rax
0x1400ce876  mov     [rbx], rsi
0x1400ce879  mov     [rax], rbx
0x1400ce87c  mov     rax, rdi
0x1400ce87f  mov     [rsi+8], rbx
0x1400ce883  jmp     short loc_1400CE88E
0x1400ce885  mov     ecx, 3
0x1400ce88a  int     29h; Win8: RtlFailFast(ecx)
0x1400ce88c  xor     eax, eax
0x1400ce88e  mov     rbx, [rsp+58h+arg_0]
0x1400ce893  add     rsp, 20h
0x1400ce897  pop     r15
0x1400ce899  pop     r14
0x1400ce89b  pop     r13
0x1400ce89d  pop     r12
0x1400ce89f  pop     rdi
0x1400ce8a0  pop     rsi
0x1400ce8a1  pop     rbp
0x1400ce8a2  retn
```
