# wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000218c`
- end: `0x140002225`
- name: `??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004434`

## callees

- `0x14000208c`
- `0x14000218c`
- `0x14000227c`
- `0x140003b3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000219a`
- `KERNEL32!GetLastError` at `0x14000219a`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastErrorHr<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  wil::details *v11; // [rsp+30h] [rbp-58h]

  LastError = GetLastError();
  v9 = LastError;
  if ( !LastError )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, (int)"wil", 0, 0, a6, v11);
    LOWORD(v9) = 668;
LABEL_4:
    v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_5;
  }
  if ( LastError > 0 )
    goto LABEL_4;
LABEL_5:
  wil::details::HrToNtStatus((wil::details *)v9);
  wil::details::ReportFailure_Base<1,0>(a1, a2);
  return v9;
}

```

## disassembly

```asm
0x14000218c  push    rbx
0x14000218e  push    rbp
0x14000218f  push    rsi
0x140002190  push    rdi
0x140002191  sub     rsp, 68h
0x140002195  mov     edi, edx
0x140002197  mov     rsi, rcx
0x14000219a  call    cs:__imp_GetLastError
0x1400021a0  mov     rbp, [rsp+88h+arg_28]
0x1400021a8  mov     ebx, eax
0x1400021aa  test    eax, eax
0x1400021ac  jnz     short loc_1400021DF
0x1400021ae  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x1400021b6  lea     r8, aWil; "wil"
0x1400021bd  mov     [rsp+88h+var_60], rbp; __int64
0x1400021c2  xor     r9d, r9d; int
0x1400021c5  mov     edx, edi; int
0x1400021c7  mov     [rsp+88h+var_68], 0; __int64
0x1400021d0  mov     rcx, rsi; int
0x1400021d3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400021d8  mov     ebx, 29Ch
0x1400021dd  jmp     short loc_1400021E1
0x1400021df  jle     short loc_1400021EA
0x1400021e1  movzx   ebx, bx
0x1400021e4  or      ebx, 80070000h
0x1400021ea  mov     ecx, ebx; this
0x1400021ec  mov     [rsp+88h+var_38], ebx
0x1400021f0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400021f5  mov     [rsp+88h+var_34], eax
0x1400021f9  mov     edx, edi
0x1400021fb  lea     rax, [rsp+88h+var_38]
0x140002200  mov     [rsp+88h+var_30], 0
0x140002208  mov     [rsp+88h+var_58], rax
0x14000220d  mov     rcx, rsi
0x140002210  mov     [rsp+88h+var_60], rbp
0x140002215  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000221a  mov     eax, ebx
0x14000221c  add     rsp, 68h
0x140002220  pop     rdi
0x140002221  pop     rsi
0x140002222  pop     rbp
0x140002223  pop     rbx
0x140002224  retn
```
