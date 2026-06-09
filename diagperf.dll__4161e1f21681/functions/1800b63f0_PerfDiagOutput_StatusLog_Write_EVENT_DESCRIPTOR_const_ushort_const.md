# PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &,ushort const *)

- ea: `0x1800b63f0`
- end: `0x1800b6495`
- name: `?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `165`
- prototype: `void __fastcall(PerfDiagOutput::StatusLog *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b67d8`

## callees

- `0x1800b63f0`
- `0x1800cf080`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800b6472`
- `ntdll!EtwEventWrite` at `0x1800b6472`
- `ntdll!EtwEventEnabled` at `0x1800b6425`
- `ntdll!EtwEventEnabled` at `0x1800b6425`

## pseudocode

```c
void __fastcall PerfDiagOutput::StatusLog::Write(
        PerfDiagOutput::StatusLog *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rax
  const struct _EVENT_DESCRIPTOR **v6; // r9
  __int64 v7; // r8
  const struct _EVENT_DESCRIPTOR *v8; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+28h] [rbp-20h]
  int v10; // [rsp+2Ch] [rbp-1Ch]

  if ( PerfDiagOutput::StatusLog::g_RegHandle
    && (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, this) )
  {
    if ( a2 )
    {
      v8 = a2;
      v5 = -1;
      do
        ++v5;
      while ( *(&a2->Id + v5) );
      v10 = 0;
      v9 = 2 * v5 + 2;
      v6 = &v8;
      v7 = 1;
    }
    else
    {
      v6 = 0;
      v7 = 0;
    }
    EtwEventWrite(PerfDiagOutput::StatusLog::g_RegHandle, this, v7, v6);
  }
}

```

## disassembly

```asm
0x1800b63f0  mov     [rsp+arg_8], rbx
0x1800b63f5  mov     [rsp+arg_10], rsi
0x1800b63fa  push    rdi
0x1800b63fb  sub     rsp, 40h
0x1800b63ff  mov     rax, cs:__security_cookie
0x1800b6406  xor     rax, rsp
0x1800b6409  mov     [rsp+48h+var_18], rax
0x1800b640e  mov     rdi, rcx
0x1800b6411  xor     esi, esi
0x1800b6413  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800b641a  mov     rbx, rdx
0x1800b641d  test    rcx, rcx
0x1800b6420  jz      short loc_1800B6478
0x1800b6422  mov     rdx, rdi
0x1800b6425  call    cs:__imp_EtwEventEnabled
0x1800b642b  test    al, al
0x1800b642d  jz      short loc_1800B6478
0x1800b642f  test    rbx, rbx
0x1800b6432  jz      short loc_1800B6462
0x1800b6434  mov     [rsp+48h+var_28], rbx
0x1800b6439  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b643d  inc     rax
0x1800b6440  cmp     [rbx+rax*2], si
0x1800b6444  jnz     short loc_1800B643D
0x1800b6446  lea     eax, ds:2[rax*2]
0x1800b644d  mov     [rsp+48h+var_1C], esi
0x1800b6451  mov     [rsp+48h+var_20], eax
0x1800b6455  lea     r9, [rsp+48h+var_28]
0x1800b645a  mov     r8d, 1
0x1800b6460  jmp     short loc_1800B6468
0x1800b6462  xor     r9d, r9d
0x1800b6465  xor     r8d, r8d
0x1800b6468  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x1800b646f  mov     rdx, rdi
0x1800b6472  call    cs:__imp_EtwEventWrite
0x1800b6478  mov     rcx, [rsp+48h+var_18]
0x1800b647d  xor     rcx, rsp; StackCookie
0x1800b6480  call    __security_check_cookie
0x1800b6485  mov     rbx, [rsp+48h+arg_8]
0x1800b648a  mov     rsi, [rsp+48h+arg_10]
0x1800b648f  add     rsp, 40h
0x1800b6493  pop     rdi
0x1800b6494  retn
```
