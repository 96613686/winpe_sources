# RasmanAddNotification

- ea: `0x18000254c`
- end: `0x18000265a`
- name: `RasmanAddNotification`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800022c4`
- `0x180023488`

## callees

- `0x18000254c`
- `0x180002ab4`
- `0x1800030d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000256a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000256a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025fe`
- `rtutils!TracePrintfExA` at `0x180002596`
- `rtutils!TracePrintfExA` at `0x1800025cc`
- `rtutils!TracePrintfExA` at `0x180002640`
- `rtutils!TracePrintfExA` at `0x180002596`
- `rtutils!TracePrintfExA` at `0x1800025cc`
- `rtutils!TracePrintfExA` at `0x180002640`

## pseudocode

```c
__int64 __fastcall RasmanAddNotification(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax

  EnterCriticalSection(&g_RasCriticalSection);
  if ( !g_fRasReferenced )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: Calling RasReferenceRasmanInternal");
    v8 = RasReferenceRasmanInternal(1);
    v9 = v8;
    if ( v8 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: RasReferenceRasmanInternal failed, Error=%d", v8);
      LeaveCriticalSection(&g_RasCriticalSection);
      return v9;
    }
    g_fRasReferenced = 1;
  }
  LeaveCriticalSection(&g_RasCriticalSection);
  v10 = SubmitLocalRequest(0x46u, a4, a1, a2, a3);
  v9 = v10;
  if ( v10 && g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasmanAddNotification: SubmitLocalRequest failed, Error: %d", v10);
  return v9;
}

```

## disassembly

```asm
0x18000254c  push    rbx
0x18000254e  push    rbp
0x18000254f  push    rsi
0x180002550  push    rdi
0x180002551  push    r14
0x180002553  sub     rsp, 30h
0x180002557  mov     r14, rcx
0x18000255a  mov     edi, r9d
0x18000255d  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180002564  mov     esi, r8d
0x180002567  mov     rbp, rdx
0x18000256a  call    cs:__imp_EnterCriticalSection
0x180002571  nop     dword ptr [rax+rax+00h]
0x180002576  cmp     cs:g_fRasReferenced, 0
0x18000257d  jnz     short loc_1800025F7
0x18000257f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002585  cmp     ecx, 0FFFFFFFFh
0x180002588  jz      short loc_1800025A2
0x18000258a  lea     r8, aRasmanaddnotif_3; "RasmanAddNotification: Calling RasRefer"...
0x180002591  mov     edx, 0Ch; dwFlags
0x180002596  call    cs:__imp_TracePrintfExA
0x18000259d  nop     dword ptr [rax+rax+00h]
0x1800025a2  mov     ecx, 1
0x1800025a7  call    RasReferenceRasmanInternal
0x1800025ac  mov     ebx, eax
0x1800025ae  test    eax, eax
0x1800025b0  jz      short loc_1800025ED
0x1800025b2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800025b8  cmp     ecx, 0FFFFFFFFh
0x1800025bb  jz      short loc_1800025D8
0x1800025bd  mov     r9d, eax
0x1800025c0  lea     r8, aRasmanaddnotif_0; "RasmanAddNotification: RasReferenceRasm"...
0x1800025c7  mov     edx, 0Ch; dwFlags
0x1800025cc  call    cs:__imp_TracePrintfExA
0x1800025d3  nop     dword ptr [rax+rax+00h]
0x1800025d8  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800025df  call    cs:__imp_LeaveCriticalSection
0x1800025e6  nop     dword ptr [rax+rax+00h]
0x1800025eb  jmp     short loc_18000264C
0x1800025ed  mov     cs:g_fRasReferenced, 1
0x1800025f7  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800025fe  call    cs:__imp_LeaveCriticalSection
0x180002605  nop     dword ptr [rax+rax+00h]
0x18000260a  mov     ecx, 46h ; 'F'
0x18000260f  mov     [rsp+58h+var_38], esi
0x180002613  mov     r9, rbp
0x180002616  mov     r8, r14
0x180002619  mov     edx, edi
0x18000261b  call    SubmitLocalRequest
0x180002620  mov     ebx, eax
0x180002622  test    eax, eax
0x180002624  jz      short loc_18000264C
0x180002626  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000262c  cmp     ecx, 0FFFFFFFFh
0x18000262f  jz      short loc_18000264C
0x180002631  mov     r9d, eax
0x180002634  lea     r8, aRasmanaddnotif_2; "RasmanAddNotification: SubmitLocalReque"...
0x18000263b  mov     edx, 0Ch; dwFlags
0x180002640  call    cs:__imp_TracePrintfExA
0x180002647  nop     dword ptr [rax+rax+00h]
0x18000264c  mov     eax, ebx
0x18000264e  add     rsp, 30h
0x180002652  pop     r14
0x180002654  pop     rdi
0x180002655  pop     rsi
0x180002656  pop     rbp
0x180002657  pop     rbx
0x180002658  retn
```
