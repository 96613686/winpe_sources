# UpdateConnectionTestedProperty

- ea: `0x18001201c`
- end: `0x180012133`
- name: `UpdateConnectionTestedProperty`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18001e640`

## callees

- `0x18001201c`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180012052`
- `rtutils!TracePrintfExA` at `0x1800120be`
- `rtutils!TracePrintfExA` at `0x18001211d`
- `rtutils!TracePrintfExA` at `0x180012052`
- `rtutils!TracePrintfExA` at `0x1800120be`
- `rtutils!TracePrintfExA` at `0x18001211d`

## string_xrefs

- `0x180012046`: `UpdateConnectionTestedProperty cannot be set for Dummy Tasks`
- `0x180012111`: `Invalid Task Type: %u`

## pseudocode

```c
void __fastcall UpdateConnectionTestedProperty(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  const wchar_t *v6; // r8
  __int64 v7; // rbp
  int v8; // eax
  int v9; // eax

  if ( (a3 & 4) != 0 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "UpdateConnectionTestedProperty cannot be set for Dummy Tasks");
    return;
  }
  if ( a3 == 2 )
  {
    v6 = L"SkipConnectionTesting";
    goto LABEL_8;
  }
  if ( a3 == 1 )
  {
    v6 = L"SkipConnectionLaunch";
LABEL_8:
    if ( a1 )
    {
      v7 = a4;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, int))(*(_QWORD *)a1 + 40LL))(
             a1,
             a2,
             v6,
             a4,
             2);
      if ( v8 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to set ConnectionTested. hr = %#x", v8);
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, __int64, int))(*(_QWORD *)a1 + 40LL))(
             a1,
             a2,
             L"HideFinishPage",
             v7,
             2);
      if ( v9 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to set HideFinishPage. hr = %#x", (unsigned int)v9);
    }
    return;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Invalid Task Type: %u", a3);
}

```

## disassembly

```asm
0x18001201c  mov     [rsp+arg_0], rbp
0x180012021  mov     [rsp+arg_8], rsi
0x180012026  push    rdi
0x180012027  sub     rsp, 30h
0x18001202b  mov     rsi, rdx
0x18001202e  mov     rdi, rcx
0x180012031  test    r8b, 4
0x180012035  jz      short loc_18001205D
0x180012037  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001203d  cmp     ecx, 0FFFFFFFFh
0x180012040  jz      loc_180012123
0x180012046  lea     r8, aUpdateconnecti; "UpdateConnectionTestedProperty cannot b"...
0x18001204d  mov     edx, 0Ch; dwFlags
0x180012052  call    cs:__imp_TracePrintfExA
0x180012058  jmp     loc_180012123
0x18001205d  cmp     r8d, 2
0x180012061  jnz     short loc_18001206C
0x180012063  lea     r8, aSkipconnection; "SkipConnectionTesting"
0x18001206a  jmp     short loc_18001207D
0x18001206c  cmp     r8d, 1
0x180012070  jnz     loc_180012103
0x180012076  lea     r8, aSkipconnection_0; "SkipConnectionLaunch"
0x18001207d  test    rdi, rdi
0x180012080  jz      loc_180012123
0x180012086  mov     rax, [rcx]
0x180012089  mov     ebp, r9d
0x18001208c  mov     r9d, r9d
0x18001208f  mov     [rsp+38h+var_18], 2
0x180012097  mov     rax, [rax+28h]
0x18001209b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a0  test    eax, eax
0x1800120a2  jns     short loc_1800120C4
0x1800120a4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800120aa  cmp     ecx, 0FFFFFFFFh
0x1800120ad  jz      short loc_1800120C4
0x1800120af  mov     r9d, eax
0x1800120b2  lea     r8, aFailedToSetCon; "Failed to set ConnectionTested. hr = %#"...
0x1800120b9  mov     edx, 0Ch; dwFlags
0x1800120be  call    cs:__imp_TracePrintfExA
0x1800120c4  mov     rax, [rdi]
0x1800120c7  lea     r8, aHidefinishpage; "HideFinishPage"
0x1800120ce  mov     r9, rbp
0x1800120d1  mov     [rsp+38h+var_18], 2
0x1800120d9  mov     rdx, rsi
0x1800120dc  mov     rcx, rdi
0x1800120df  mov     rax, [rax+28h]
0x1800120e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e8  test    eax, eax
0x1800120ea  jns     short loc_180012123
0x1800120ec  mov     ecx, cs:g_dwTraceId
0x1800120f2  cmp     ecx, 0FFFFFFFFh
0x1800120f5  jz      short loc_180012123
0x1800120f7  mov     r9d, eax
0x1800120fa  lea     r8, aFailedToSetHid; "Failed to set HideFinishPage. hr = %#x"
0x180012101  jmp     short loc_180012118
0x180012103  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012109  cmp     ecx, 0FFFFFFFFh
0x18001210c  jz      short loc_180012123
0x18001210e  mov     r9d, r8d
0x180012111  lea     r8, aInvalidTaskTyp; "Invalid Task Type: %u"
0x180012118  mov     edx, 0Ch; dwFlags
0x18001211d  call    cs:__imp_TracePrintfExA
0x180012123  mov     rbp, [rsp+38h+arg_0]
0x180012128  mov     rsi, [rsp+38h+arg_8]
0x18001212d  add     rsp, 30h
0x180012131  pop     rdi
0x180012132  retn
```
