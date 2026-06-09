# CIncomingConnectionsTask::CanAllowICC(void)

- ea: `0x18001f8ec`
- end: `0x18001f94b`
- name: `?CanAllowICC@CIncomingConnectionsTask@@IEAAHXZ`
- size: `95`
- prototype: `__int64 __fastcall(CIncomingConnectionsTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f960`
- `0x18001fa60`

## callees

- `0x18001f8ec`
- `0x18002c60c`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001f937`
- `rtutils!TracePrintfExA` at `0x18001f937`

## string_xrefs

- `0x18001f92b`: `CIncomingConnectionsTask::CanAllowICC: StarterEdition`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionsTask::CanAllowICC(CIncomingConnectionsTask *this)
{
  unsigned __int64 v1; // rax
  __int64 v2; // rcx

  if ( !dword_18004DC40 && (unsigned int)LoadSkuAndRole(this) )
    return 1;
  v1 = (unsigned int)(dword_18004DA80 - 11);
  if ( (unsigned int)v1 > 0x37 )
    return 1;
  v2 = 0x80001000000001LL;
  if ( !_bittest64(&v2, v1) )
    return 1;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CIncomingConnectionsTask::CanAllowICC: StarterEdition");
  return 0;
}

```

## disassembly

```asm
0x18001f8ec  sub     rsp, 28h
0x18001f8f0  cmp     cs:dword_18004DC40, 0
0x18001f8f7  jnz     short loc_18001F902
0x18001f8f9  call    LoadSkuAndRole
0x18001f8fe  test    eax, eax
0x18001f900  jnz     short loc_18001F941
0x18001f902  mov     eax, cs:dword_18004DA80
0x18001f908  add     eax, 0FFFFFFF5h
0x18001f90b  cmp     eax, 37h ; '7'
0x18001f90e  ja      short loc_18001F941
0x18001f910  mov     rcx, 80001000000001h
0x18001f91a  bt      rcx, rax
0x18001f91e  jnb     short loc_18001F941
0x18001f920  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f926  cmp     ecx, 0FFFFFFFFh
0x18001f929  jz      short loc_18001F93D
0x18001f92b  lea     r8, aCincomingconne_1; "CIncomingConnectionsTask::CanAllowICC: "...
0x18001f932  mov     edx, 0Ch; dwFlags
0x18001f937  call    cs:__imp_TracePrintfExA
0x18001f93d  xor     eax, eax
0x18001f93f  jmp     short loc_18001F946
0x18001f941  mov     eax, 1
0x18001f946  add     rsp, 28h
0x18001f94a  retn
```
