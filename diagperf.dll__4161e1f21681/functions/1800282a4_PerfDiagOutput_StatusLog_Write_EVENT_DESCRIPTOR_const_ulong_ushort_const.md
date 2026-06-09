# PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ulong,ushort const *)

- ea: `0x1800282a4`
- end: `0x180028360`
- name: `?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@KPEBG@Z`
- size: `188`
- prototype: `void __fastcall(PerfDiagOutput::StatusLog *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned int, const unsigned __int16 *)`
- caller_count: `24`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016dec`
- `0x1800279d8`
- `0x1800286b8`
- `0x18002b580`
- `0x18002f06c`
- `0x180030840`
- `0x180031aec`
- `0x1800375cc`
- `0x180041034`
- `0x180043ea8`
- `0x1800ae878`
- `0x1800ae914`
- `0x1800b4410`
- `0x1800b4ec0`
- `0x1800b4f00`
- `0x1800b67d8`
- `0x1800b9ae0`
- `0x1800b9db0`
- `0x1800ba54c`
- `0x1800ba5f0`
- `0x1800c25a8`
- `0x1800c277c`
- `0x1800c49c4`
- `0x1800c96e0`

## callees

- `0x1800282a4`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002833d`
- `ntdll!EtwEventWrite` at `0x18002833d`
- `ntdll!EtwEventEnabled` at `0x1800282dd`
- `ntdll!EtwEventEnabled` at `0x1800282dd`

## pseudocode

```c
void __fastcall PerfDiagOutput::StatusLog::Write(
        PerfDiagOutput::StatusLog *this,
        const struct _EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rax
  __int64 v7; // r8
  _QWORD v8[3]; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+38h] [rbp-20h]
  int v10; // [rsp+3Ch] [rbp-1Ch]
  int v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = (int)a2;
  if ( PerfDiagOutput::StatusLog::g_RegHandle
    && (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, this) )
  {
    v8[1] = 4;
    v8[0] = &v11;
    if ( a3 )
    {
      v8[2] = a3;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(a3 + 2 * v6) );
      v10 = 0;
      v9 = 2 * v6 + 2;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
    EtwEventWrite(PerfDiagOutput::StatusLog::g_RegHandle, this, v7, v8);
  }
}

```

## disassembly

```asm
0x1800282a4  mov     [rsp+arg_10], rbx
0x1800282a9  mov     [rsp+arg_18], rsi
0x1800282ae  mov     [rsp+arg_8], edx
0x1800282b2  push    rdi
0x1800282b3  sub     rsp, 50h
0x1800282b7  mov     rax, cs:__security_cookie
0x1800282be  xor     rax, rsp
0x1800282c1  mov     [rsp+58h+var_18], rax
0x1800282c6  mov     rdi, rcx
0x1800282c9  xor     esi, esi
0x1800282cb  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800282d2  mov     rbx, r8
0x1800282d5  test    rcx, rcx
0x1800282d8  jz      short loc_180028343
0x1800282da  mov     rdx, rdi
0x1800282dd  call    cs:__imp_EtwEventEnabled
0x1800282e3  test    al, al
0x1800282e5  jz      short loc_180028343
0x1800282e7  mov     [rsp+58h+var_30], 4
0x1800282f0  lea     rax, [rsp+58h+arg_8]
0x1800282f5  mov     [rsp+58h+var_38], rax
0x1800282fa  test    rbx, rbx
0x1800282fd  jz      short loc_180028328
0x1800282ff  mov     [rsp+58h+var_28], rbx
0x180028304  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028308  inc     rax
0x18002830b  cmp     [rbx+rax*2], si
0x18002830f  jnz     short loc_180028308
0x180028311  lea     eax, ds:2[rax*2]
0x180028318  mov     [rsp+58h+var_1C], esi
0x18002831c  mov     [rsp+58h+var_20], eax
0x180028320  mov     r8d, 2
0x180028326  jmp     short loc_18002832E
0x180028328  mov     r8d, 1
0x18002832e  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x180028335  lea     r9, [rsp+58h+var_38]
0x18002833a  mov     rdx, rdi
0x18002833d  call    cs:__imp_EtwEventWrite
0x180028343  mov     rcx, [rsp+58h+var_18]
0x180028348  xor     rcx, rsp; StackCookie
0x18002834b  call    __security_check_cookie
0x180028350  mov     rbx, [rsp+58h+arg_10]
0x180028355  mov     rsi, [rsp+58h+arg_18]
0x18002835a  add     rsp, 50h
0x18002835e  pop     rdi
0x18002835f  retn
```
