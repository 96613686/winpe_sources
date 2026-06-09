# CMBPropertyWriter::WritePropertyShort(void)

- ea: `0x180030634`
- end: `0x180030801`
- name: `?WritePropertyShort@CMBPropertyWriter@@AEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(CMBPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002f998`

## callees

- `0x180006d08`
- `0x180008a08`
- `0x18002bdb4`
- `0x180030208`
- `0x180030634`
- `0x1800309d0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800306a6`
- `msvcrt!wcschr` at `0x1800306a6`

## string_xrefs

- `0x180030711`: `			<Property       InheritsPropertiesFrom ="IIsConfigObject:`

## pseudocode

```c
__int64 __fastcall CMBPropertyWriter::WritePropertyShort(
        CMBPropertyWriter *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  wchar_t *v4; // r15
  __int64 v5; // r14
  _WORD *v7; // rbp
  __int64 v8; // rdi
  wchar_t *v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  int v12; // ebx
  void *Block; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int16 v15[28]; // [rsp+38h] [rbp-70h] BYREF

  v4 = (wchar_t *)*((_QWORD *)this + 1);
  v5 = -1;
  Block = 0;
  v7 = 0;
  if ( v4 )
  {
    v9 = wcschr(v4, 0x2Cu);
    v10 = *((_QWORD *)this + 1);
    if ( v9 )
    {
      v8 = ((__int64)v9 - v10) >> 1;
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v10 + 2 * v8) );
    }
  }
  else
  {
    CMBPropertyWriter::CreateUnknownName(this, v15, 0x19u, a4);
    v8 = -1;
    v4 = v15;
    do
      ++v8;
    while ( v15[v8] );
  }
  if ( !*((_DWORD *)this + 15)
    || (v11 = CWriterGlobalHelper::FlagToString(
                *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                0x200u,
                (unsigned __int16 **)&Block,
                L"COLUMNMETA",
                0xCu),
        v7 = Block,
        v12 = v11,
        v11 >= 0) )
  {
    v12 = CWriter::WriteToFile(
            *(CWriter **)this,
            L"\t\t\t<Property       InheritsPropertiesFrom =\"IIsConfigObject:",
            g_cchBeginPropertyShort,
            0);
    if ( v12 >= 0 )
    {
      v12 = CWriter::WriteToFile(*(CWriter **)this, v4, v8, 0);
      if ( v12 >= 0 )
      {
        if ( !*((_DWORD *)this + 15) )
          goto LABEL_19;
        v12 = CWriter::WriteToFile(*(CWriter **)this, L"\"\t\t\tMetaFlagsEx=\"", g_cchPropMetaFlagsExEq, 0);
        if ( v12 >= 0 )
        {
          v12 = CWriter::WriteToFile(*(CWriter **)this, L"| ", g_cchOr, 0);
          if ( v12 >= 0 )
          {
            do
              ++v5;
            while ( v7[v5] );
            v12 = CWriter::WriteToFile(*(CWriter **)this, v7, v5, 0);
            if ( v12 >= 0 )
LABEL_19:
              v12 = CWriter::WriteToFile(*(CWriter **)this, L"\"/>\r\n", g_cchEndPropertyShort, 0);
          }
        }
      }
    }
  }
  if ( v7 )
    operator delete(v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180030634  mov     r11, rsp
0x180030637  mov     [r11+10h], rbx
0x18003063b  mov     [r11+18h], rbp
0x18003063f  push    rsi
0x180030640  push    rdi
0x180030641  push    r12
0x180030643  push    r14
0x180030645  push    r15
0x180030647  sub     rsp, 80h
0x18003064e  mov     rax, cs:__security_cookie
0x180030655  xor     rax, rsp
0x180030658  mov     [rsp+0A8h+var_38], rax
0x18003065d  mov     r15, [rcx+8]
0x180030661  xor     r12d, r12d
0x180030664  or      r14, 0FFFFFFFFFFFFFFFFh
0x180030668  mov     [r11-78h], r12
0x18003066c  mov     rsi, rcx
0x18003066f  mov     ebp, r12d
0x180030672  test    r15, r15
0x180030675  jnz     short loc_18003069E
0x180030677  lea     r8d, [r12+19h]; unsigned int
0x18003067c  lea     rdx, [r11-70h]; unsigned __int16 *
0x180030680  call    ?CreateUnknownName@CMBPropertyWriter@@AEAAXPEAGKK@Z; CMBPropertyWriter::CreateUnknownName(ushort *,ulong,ulong)
0x180030685  lea     rax, [rsp+0A8h+var_70]
0x18003068a  mov     rdi, r14
0x18003068d  lea     r15, [rsp+0A8h+var_70]
0x180030692  inc     rdi
0x180030695  cmp     [rax+rdi*2], r12w
0x18003069a  jnz     short loc_180030692
0x18003069c  jmp     short loc_1800306CD
0x18003069e  mov     edx, 2Ch ; ','; Ch
0x1800306a3  mov     rcx, r15; Str
0x1800306a6  call    cs:__imp_wcschr
0x1800306ac  mov     rdi, rax
0x1800306af  mov     rax, [rsi+8]
0x1800306b3  test    rdi, rdi
0x1800306b6  jnz     short loc_1800306C7
0x1800306b8  mov     rdi, r14
0x1800306bb  inc     rdi
0x1800306be  cmp     [rax+rdi*2], r12w
0x1800306c3  jnz     short loc_1800306BB
0x1800306c5  jmp     short loc_1800306CD
0x1800306c7  sub     rdi, rax
0x1800306ca  sar     rdi, 1
0x1800306cd  cmp     [rsi+3Ch], r12d
0x1800306d1  jz      short loc_18003070A
0x1800306d3  mov     rcx, [rsi]
0x1800306d6  lea     r9, aColumnmeta; "COLUMNMETA"
0x1800306dd  lea     r8, [rsp+0A8h+Block]; unsigned __int16 **
0x1800306e2  mov     [rsp+0A8h+var_88], 0Ch; unsigned int
0x1800306ea  mov     edx, 200h; unsigned int
0x1800306ef  mov     rcx, [rcx+10040h]; this
0x1800306f6  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x1800306fb  mov     rbp, [rsp+0A8h+Block]
0x180030700  mov     ebx, eax
0x180030702  test    eax, eax
0x180030704  js      loc_1800307C9
0x18003070a  mov     r8d, cs:?g_cchBeginPropertyShort@@3KA; unsigned int
0x180030711  lea     rdx, aPropertyInheri; "\t\t\t<Property       InheritsPropertie"...
0x180030718  mov     rcx, [rsi]; this
0x18003071b  xor     r9d, r9d; int
0x18003071e  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x180030723  mov     ebx, eax
0x180030725  test    eax, eax
0x180030727  js      loc_1800307C9
0x18003072d  mov     rcx, [rsi]; this
0x180030730  mov     r8d, edi; unsigned int
0x180030733  xor     r9d, r9d; int
0x180030736  mov     rdx, r15; void *
0x180030739  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18003073e  mov     ebx, eax
0x180030740  test    eax, eax
0x180030742  js      loc_1800307C9
0x180030748  cmp     [rsi+3Ch], r12d
0x18003074c  jz      short loc_1800307AE
0x18003074e  mov     r8d, cs:?g_cchPropMetaFlagsExEq@@3KA; unsigned int
0x180030755  lea     rdx, aMetaflagsex; "\"\t\t\tMetaFlagsEx=\""
0x18003075c  mov     rcx, [rsi]; this
0x18003075f  xor     r9d, r9d; int
0x180030762  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x180030767  mov     ebx, eax
0x180030769  test    eax, eax
0x18003076b  js      short loc_1800307C9
0x18003076d  mov     r8d, cs:?g_cchOr@@3KA; unsigned int
0x180030774  lea     rdx, asc_180040E08; "| "
0x18003077b  mov     rcx, [rsi]; this
0x18003077e  xor     r9d, r9d; int
0x180030781  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x180030786  mov     ebx, eax
0x180030788  test    eax, eax
0x18003078a  js      short loc_1800307C9
0x18003078c  inc     r14
0x18003078f  cmp     [rbp+r14*2+0], r12w
0x180030795  jnz     short loc_18003078C
0x180030797  mov     rcx, [rsi]; this
0x18003079a  xor     r9d, r9d; int
0x18003079d  mov     r8d, r14d; unsigned int
0x1800307a0  mov     rdx, rbp; void *
0x1800307a3  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x1800307a8  mov     ebx, eax
0x1800307aa  test    eax, eax
0x1800307ac  js      short loc_1800307C9
0x1800307ae  mov     r8d, cs:?g_cchEndPropertyShort@@3KA; unsigned int
0x1800307b5  lea     rdx, asc_180040BF8; "\"/>\r\n"
0x1800307bc  mov     rcx, [rsi]; this
0x1800307bf  xor     r9d, r9d; int
0x1800307c2  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x1800307c7  mov     ebx, eax
0x1800307c9  test    rbp, rbp
0x1800307cc  jz      short loc_1800307D6
0x1800307ce  mov     rcx, rbp; Block
0x1800307d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800307d6  mov     eax, ebx
0x1800307d8  mov     rcx, [rsp+0A8h+var_38]
0x1800307dd  xor     rcx, rsp; StackCookie
0x1800307e0  call    __security_check_cookie
0x1800307e5  lea     r11, [rsp+0A8h+var_28]
0x1800307ed  mov     rbx, [r11+38h]
0x1800307f1  mov     rbp, [r11+40h]
0x1800307f5  mov     rsp, r11
0x1800307f8  pop     r15
0x1800307fa  pop     r14
0x1800307fc  pop     r12
0x1800307fe  pop     rdi
0x1800307ff  pop     rsi
0x180030800  retn
```
