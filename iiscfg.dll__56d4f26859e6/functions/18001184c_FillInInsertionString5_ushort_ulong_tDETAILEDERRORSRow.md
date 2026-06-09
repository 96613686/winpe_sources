# FillInInsertionString5(ushort *,ulong,tDETAILEDERRORSRow &)

- ea: `0x18001184c`
- end: `0x180011b32`
- name: `?FillInInsertionString5@@YAXPEAGKAEAUtDETAILEDERRORSRow@@@Z`
- size: `742`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, struct tDETAILEDERRORSRow *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012734`
- `0x1800139c0`
- `0x180013d80`

## callees

- `0x18001184c`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x1800118a8`
- `msvcrt!_snwprintf_s` at `0x1800118fc`
- `msvcrt!_snwprintf_s` at `0x18001195b`
- `msvcrt!_snwprintf_s` at `0x1800119a6`
- `msvcrt!_snwprintf_s` at `0x1800119f1`
- `msvcrt!_snwprintf_s` at `0x180011a39`
- `msvcrt!_snwprintf_s` at `0x180011a81`
- `msvcrt!_snwprintf_s` at `0x180011ac9`
- `msvcrt!_snwprintf_s` at `0x180011b11`
- `msvcrt!_snwprintf_s` at `0x1800118a8`
- `msvcrt!_snwprintf_s` at `0x1800118fc`
- `msvcrt!_snwprintf_s` at `0x18001195b`
- `msvcrt!_snwprintf_s` at `0x1800119a6`
- `msvcrt!_snwprintf_s` at `0x1800119f1`
- `msvcrt!_snwprintf_s` at `0x180011a39`
- `msvcrt!_snwprintf_s` at `0x180011a81`
- `msvcrt!_snwprintf_s` at `0x180011ac9`
- `msvcrt!_snwprintf_s` at `0x180011b11`

## string_xrefs

- `0x1800119e2`: `ConfigurationSource`

## pseudocode

```c
void __fastcall FillInInsertionString5(unsigned __int16 *a1, __int64 a2, struct tDETAILEDERRORSRow *a3)
{
  _DWORD *v5; // rax
  int v6; // eax
  wchar_t *v7; // rbx
  _DWORD *v8; // rcx
  int v9; // eax
  _DWORD *v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  _DWORD *v14; // rcx
  int v15; // eax
  _DWORD *v16; // rcx
  int v17; // eax
  _DWORD *v18; // rcx
  int v19; // eax
  _DWORD *v20; // rcx
  __int64 v21; // [rsp+28h] [rbp-30h]

  if ( !*((_QWORD *)a3 + 18) && a1 )
  {
    *a1 = 0;
    v5 = (_DWORD *)*((_QWORD *)a3 + 19);
    if ( v5 )
    {
      v6 = _snwprintf_s(a1, 0x400u, 0x400u, L"\r\n%-20s: 0x%08X", L"ErrorCode", *v5);
      if ( v6 < 0 )
        v6 = -v6;
      v7 = &a1[v6];
    }
    else
    {
      v7 = a1;
    }
    v8 = (_DWORD *)*((_QWORD *)a3 + 20);
    if ( v8 )
    {
      LODWORD(v21) = *v8;
      v9 = _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %d", L"Interceptor", v21);
      if ( v9 < 0 )
        v9 = -v9;
      v7 += v9;
    }
    v10 = (_DWORD *)*((_QWORD *)a3 + 22);
    if ( v10 && *v10 < 3u )
    {
      v11 = _snwprintf_s(
              v7,
              1024 - (v7 - a1),
              1024 - (v7 - a1),
              L"\r\n%-20s: %s",
              L"OperationType",
              `FillInInsertionString5'::`2'::pwszOperationType[*v10]);
      if ( v11 < 0 )
        v11 = -v11;
      v7 += v11;
    }
    if ( *((_QWORD *)a3 + 23) )
    {
      v12 = _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %s", L"Table", *((_QWORD *)a3 + 23));
      if ( v12 < 0 )
        v12 = -v12;
      v7 += v12;
    }
    if ( *((_QWORD *)a3 + 24) )
    {
      v13 = _snwprintf_s(
              v7,
              1024 - (v7 - a1),
              1024 - (v7 - a1),
              L"\r\n%-20s: %s",
              L"ConfigurationSource",
              *((_QWORD *)a3 + 24));
      if ( v13 < 0 )
        v13 = -v13;
      v7 += v13;
    }
    v14 = (_DWORD *)*((_QWORD *)a3 + 25);
    if ( v14 )
    {
      LODWORD(v21) = *v14;
      v15 = _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %d", L"Row", v21);
      if ( v15 < 0 )
        v15 = -v15;
      v7 += v15;
    }
    v16 = (_DWORD *)*((_QWORD *)a3 + 26);
    if ( v16 )
    {
      LODWORD(v21) = *v16;
      v17 = _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %d", L"Column", v21);
      if ( v17 < 0 )
        v17 = -v17;
      v7 += v17;
    }
    v18 = (_DWORD *)*((_QWORD *)a3 + 27);
    if ( v18 )
    {
      LODWORD(v21) = *v18;
      v19 = _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %d", L"MajorVersion", v21);
      if ( v19 < 0 )
        v19 = -v19;
      v7 += v19;
    }
    v20 = (_DWORD *)*((_QWORD *)a3 + 28);
    if ( v20 )
    {
      LODWORD(v21) = *v20;
      _snwprintf_s(v7, 1024 - (v7 - a1), 1024 - (v7 - a1), L"\r\n%-20s: %d", L"MinorVersion", v21);
    }
    a1[1023] = 0;
    *((_QWORD *)a3 + 18) = a1;
  }
}

```

## disassembly

```asm
0x18001184c  push    rbx
0x18001184e  push    rbp
0x18001184f  push    rsi
0x180011850  push    rdi
0x180011851  push    r15
0x180011853  sub     rsp, 30h
0x180011857  cmp     qword ptr [r8+90h], 0
0x18001185f  mov     rsi, r8
0x180011862  mov     rdi, rcx
0x180011865  jnz     loc_180011B27
0x18001186b  test    rcx, rcx
0x18001186e  jz      loc_180011B27
0x180011874  xor     eax, eax
0x180011876  mov     ebp, 400h
0x18001187b  mov     [rcx], ax
0x18001187e  mov     rax, [r8+98h]
0x180011885  test    rax, rax
0x180011888  jz      short loc_1800118BC
0x18001188a  mov     eax, [rax]
0x18001188c  lea     r9, a20s0x08x; "\r\n%-20s: 0x%08X"
0x180011893  mov     dword ptr [rsp+58h+var_30], eax
0x180011897  mov     r8d, ebp; MaxCount
0x18001189a  lea     rax, aErrorcode; "ErrorCode"
0x1800118a1  mov     edx, ebp; BufferCount
0x1800118a3  mov     [rsp+58h+var_38], rax
0x1800118a8  call    cs:__imp__snwprintf_s
0x1800118ae  test    eax, eax
0x1800118b0  jns     short loc_1800118B4
0x1800118b2  neg     eax
0x1800118b4  cdqe
0x1800118b6  lea     rbx, [rdi+rax*2]
0x1800118ba  jmp     short loc_1800118BF
0x1800118bc  mov     rbx, rdi
0x1800118bf  mov     rcx, [rsi+0A0h]
0x1800118c6  lea     r15, a20sD; "\r\n%-20s: %d"
0x1800118cd  test    rcx, rcx
0x1800118d0  jz      short loc_18001190E
0x1800118d2  mov     rax, rbx
0x1800118d5  mov     rdx, rbp
0x1800118d8  sub     rax, rdi
0x1800118db  mov     r9, r15; Format
0x1800118de  sar     rax, 1
0x1800118e1  sub     rdx, rax; BufferCount
0x1800118e4  mov     eax, [rcx]
0x1800118e6  mov     dword ptr [rsp+58h+var_30], eax
0x1800118ea  mov     r8, rdx; MaxCount
0x1800118ed  lea     rax, aInterceptor; "Interceptor"
0x1800118f4  mov     rcx, rbx; Buffer
0x1800118f7  mov     [rsp+58h+var_38], rax
0x1800118fc  call    cs:__imp__snwprintf_s
0x180011902  test    eax, eax
0x180011904  jns     short loc_180011908
0x180011906  neg     eax
0x180011908  cdqe
0x18001190a  lea     rbx, [rbx+rax*2]
0x18001190e  mov     rax, [rsi+0B0h]
0x180011915  test    rax, rax
0x180011918  jz      short loc_18001196D
0x18001191a  mov     ecx, [rax]
0x18001191c  cmp     ecx, 3
0x18001191f  jnb     short loc_18001196D
0x180011921  mov     rax, rbx
0x180011924  lea     r9, a20sS; "\r\n%-20s: %s"
0x18001192b  sub     rax, rdi
0x18001192e  mov     rdx, rbp
0x180011931  sar     rax, 1
0x180011934  sub     rdx, rax; BufferCount
0x180011937  mov     eax, ecx
0x180011939  lea     rcx, ?pwszOperationType@?1??FillInInsertionString5@@YAXPEAGKAEAUtDETAILEDERRORSRow@@@Z@4PAPEBGA; ushort const * near * `FillInInsertionString5(ushort *,ulong,tDETAILEDERRORSRow &)'::`2'::pwszOperationType
0x180011940  mov     r8, rdx; MaxCount
0x180011943  mov     rax, [rcx+rax*8]
0x180011947  mov     rcx, rbx; Buffer
0x18001194a  mov     [rsp+58h+var_30], rax
0x18001194f  lea     rax, aOperationtype; "OperationType"
0x180011956  mov     [rsp+58h+var_38], rax
0x18001195b  call    cs:__imp__snwprintf_s
0x180011961  test    eax, eax
0x180011963  jns     short loc_180011967
0x180011965  neg     eax
0x180011967  cdqe
0x180011969  lea     rbx, [rbx+rax*2]
0x18001196d  mov     rcx, [rsi+0B8h]
0x180011974  test    rcx, rcx
0x180011977  jz      short loc_1800119B8
0x180011979  mov     [rsp+58h+var_30], rcx
0x18001197e  lea     r9, a20sS; "\r\n%-20s: %s"
0x180011985  mov     rax, rbx
0x180011988  mov     rdx, rbp
0x18001198b  sub     rax, rdi
0x18001198e  mov     rcx, rbx; Buffer
0x180011991  sar     rax, 1
0x180011994  sub     rdx, rax; BufferCount
0x180011997  lea     rax, aTable; "Table"
0x18001199e  mov     r8, rdx; MaxCount
0x1800119a1  mov     [rsp+58h+var_38], rax
0x1800119a6  call    cs:__imp__snwprintf_s
0x1800119ac  test    eax, eax
0x1800119ae  jns     short loc_1800119B2
0x1800119b0  neg     eax
0x1800119b2  cdqe
0x1800119b4  lea     rbx, [rbx+rax*2]
0x1800119b8  mov     rcx, [rsi+0C0h]
0x1800119bf  test    rcx, rcx
0x1800119c2  jz      short loc_180011A03
0x1800119c4  mov     [rsp+58h+var_30], rcx
0x1800119c9  lea     r9, a20sS; "\r\n%-20s: %s"
0x1800119d0  mov     rax, rbx
0x1800119d3  mov     rdx, rbp
0x1800119d6  sub     rax, rdi
0x1800119d9  mov     rcx, rbx; Buffer
0x1800119dc  sar     rax, 1
0x1800119df  sub     rdx, rax; BufferCount
0x1800119e2  lea     rax, aConfigurations; "ConfigurationSource"
0x1800119e9  mov     r8, rdx; MaxCount
0x1800119ec  mov     [rsp+58h+var_38], rax
0x1800119f1  call    cs:__imp__snwprintf_s
0x1800119f7  test    eax, eax
0x1800119f9  jns     short loc_1800119FD
0x1800119fb  neg     eax
0x1800119fd  cdqe
0x1800119ff  lea     rbx, [rbx+rax*2]
0x180011a03  mov     rcx, [rsi+0C8h]
0x180011a0a  test    rcx, rcx
0x180011a0d  jz      short loc_180011A4B
0x180011a0f  mov     rax, rbx
0x180011a12  mov     rdx, rbp
0x180011a15  sub     rax, rdi
0x180011a18  mov     r9, r15; Format
0x180011a1b  sar     rax, 1
0x180011a1e  sub     rdx, rax; BufferCount
0x180011a21  mov     eax, [rcx]
0x180011a23  mov     dword ptr [rsp+58h+var_30], eax
0x180011a27  mov     r8, rdx; MaxCount
0x180011a2a  lea     rax, aRow; "Row"
0x180011a31  mov     rcx, rbx; Buffer
0x180011a34  mov     [rsp+58h+var_38], rax
0x180011a39  call    cs:__imp__snwprintf_s
0x180011a3f  test    eax, eax
0x180011a41  jns     short loc_180011A45
0x180011a43  neg     eax
0x180011a45  cdqe
0x180011a47  lea     rbx, [rbx+rax*2]
0x180011a4b  mov     rcx, [rsi+0D0h]
0x180011a52  test    rcx, rcx
0x180011a55  jz      short loc_180011A93
0x180011a57  mov     rax, rbx
0x180011a5a  mov     rdx, rbp
0x180011a5d  sub     rax, rdi
0x180011a60  mov     r9, r15; Format
0x180011a63  sar     rax, 1
0x180011a66  sub     rdx, rax; BufferCount
0x180011a69  mov     eax, [rcx]
0x180011a6b  mov     dword ptr [rsp+58h+var_30], eax
0x180011a6f  mov     r8, rdx; MaxCount
0x180011a72  lea     rax, aColumn; "Column"
0x180011a79  mov     rcx, rbx; Buffer
0x180011a7c  mov     [rsp+58h+var_38], rax
0x180011a81  call    cs:__imp__snwprintf_s
0x180011a87  test    eax, eax
0x180011a89  jns     short loc_180011A8D
0x180011a8b  neg     eax
0x180011a8d  cdqe
0x180011a8f  lea     rbx, [rbx+rax*2]
0x180011a93  mov     rcx, [rsi+0D8h]
0x180011a9a  test    rcx, rcx
0x180011a9d  jz      short loc_180011ADB
0x180011a9f  mov     rax, rbx
0x180011aa2  mov     rdx, rbp
0x180011aa5  sub     rax, rdi
0x180011aa8  mov     r9, r15; Format
0x180011aab  sar     rax, 1
0x180011aae  sub     rdx, rax; BufferCount
0x180011ab1  mov     eax, [rcx]
0x180011ab3  mov     dword ptr [rsp+58h+var_30], eax
0x180011ab7  mov     r8, rdx; MaxCount
0x180011aba  lea     rax, aMajorversion; "MajorVersion"
0x180011ac1  mov     rcx, rbx; Buffer
0x180011ac4  mov     [rsp+58h+var_38], rax
0x180011ac9  call    cs:__imp__snwprintf_s
0x180011acf  test    eax, eax
0x180011ad1  jns     short loc_180011AD5
0x180011ad3  neg     eax
0x180011ad5  cdqe
0x180011ad7  lea     rbx, [rbx+rax*2]
0x180011adb  mov     rcx, [rsi+0E0h]
0x180011ae2  test    rcx, rcx
0x180011ae5  jz      short loc_180011B17
0x180011ae7  mov     rax, rbx
0x180011aea  mov     r9, r15; Format
0x180011aed  sub     rax, rdi
0x180011af0  sar     rax, 1
0x180011af3  sub     rbp, rax
0x180011af6  mov     eax, [rcx]
0x180011af8  mov     dword ptr [rsp+58h+var_30], eax
0x180011afc  mov     r8, rbp; MaxCount
0x180011aff  lea     rax, aMinorversion; "MinorVersion"
0x180011b06  mov     rdx, rbp; BufferCount
0x180011b09  mov     rcx, rbx; Buffer
0x180011b0c  mov     [rsp+58h+var_38], rax
0x180011b11  call    cs:__imp__snwprintf_s
0x180011b17  xor     eax, eax
0x180011b19  mov     [rdi+7FEh], ax
0x180011b20  mov     [rsi+90h], rdi
0x180011b27  add     rsp, 30h
0x180011b2b  pop     r15
0x180011b2d  pop     rdi
0x180011b2e  pop     rsi
0x180011b2f  pop     rbp
0x180011b30  pop     rbx
0x180011b31  retn
```
