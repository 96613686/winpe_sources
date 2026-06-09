# SleepStudyXmlReporter::WriteFxComponents(ulong,std::vector<FxComponentData *,std::allocator<FxComponentData *>> const &)

- ea: `0x180047d4c`
- end: `0x180047f56`
- name: `?WriteFxComponents@SleepStudyXmlReporter@@IEAAKKAEBV?$vector@PEAUFxComponentData@@V?$allocator@PEAUFxComponentData@@@std@@@std@@@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004910c`

## callees

- `0x180008740`
- `0x18000f730`
- `0x180010ac4`
- `0x18001107c`
- `0x1800110c4`
- `0x180011948`
- `0x180012020`
- `0x18001292c`
- `0x180012a98`
- `0x180047d4c`
- `0x18004d8c0`

## string_xrefs

- `0x180047f31`: `</ComponentBlockers>\n`
- `0x180047d86`: `<Component Index="`
- `0x180047ee8`: `<ComponentBlockers>\n`

## pseudocode

```c
__int64 __fastcall SleepStudyXmlReporter::WriteFxComponents(__int64 a1, unsigned int a2, __int64 **a3)
{
  __int64 *v3; // rbx
  XmlReporter *v4; // rdi
  int v5; // r15d
  unsigned int v7; // r12d
  __int64 v10; // rsi
  XmlReporter *v11; // rcx
  double ScenarioActiveTimePercent; // xmm0_8
  double v13; // xmm0_8
  double SegmentActiveTimePercent; // xmm0_8
  double v15; // xmm0_8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  const unsigned __int16 *v19; // rdx
  __int64 *i; // rbx

  v3 = *a3;
  v4 = (XmlReporter *)(a1 + 16);
  v5 = 0;
  v7 = 0;
  while ( v3 != a3[1] )
  {
    v10 = *v3;
    v4 = (XmlReporter *)(a1 + 16);
    XmlReporter::WriteTabbedRawString((XmlReporter *)(a1 + 16), a2, L"<Component Index=\"");
    XmlReporter::WriteInteger((XmlReporter *)(a1 + 16), *(_DWORD *)(v10 + 584));
    v11 = (XmlReporter *)(a1 + 16);
    if ( *(_QWORD *)(v10 + 120) == -1 )
    {
      XmlReporter::WriteRawString(v11, L"\" ScenarioActiveTimePercent=\"invalid");
      XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" SegmentActiveTimePercent=\"invalid");
      XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" ActiveTime=\"invalid");
    }
    else
    {
      XmlReporter::WriteRawString(v11, L"\" ScenarioActiveTimePercent=\"");
      ScenarioActiveTimePercent = BlockerData::GetScenarioActiveTimePercent((BlockerData *)v10);
      v13 = floor(ScenarioActiveTimePercent + 0.5);
      XmlReporter::WriteInteger((XmlReporter *)(a1 + 16), (int)v13);
      XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" SegmentActiveTimePercent=\"");
      SegmentActiveTimePercent = BlockerData::GetSegmentActiveTimePercent((BlockerData *)v10);
      v15 = floor(SegmentActiveTimePercent + 0.5);
      XmlReporter::WriteInteger((XmlReporter *)(a1 + 16), (int)v15);
      XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" ActiveTime=\"");
      XmlReporter::WriteInteger64((XmlReporter *)(a1 + 16), *(_QWORD *)(v10 + 120));
    }
    XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" ActivityLevel=\"");
    if ( (int)BlockerData::GetActivityLevel(v10) >= 5 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18);
    if ( (int)BlockerData::GetActivityLevel(v10) < 0 || (int)BlockerData::GetActivityLevel(v10) >= 5 )
      v19 = L"unrecognized";
    else
      v19 = (&ActivityLevelNames)[(int)BlockerData::GetActivityLevel(v10)];
    XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), v19);
    XmlReporter::WriteRawString((XmlReporter *)(a1 + 16), L"\" />\n");
    if ( (__int64)(*(_QWORD *)(v10 + 64) - *(_QWORD *)(v10 + 56)) >> 3 )
      v5 = 1;
    ++v3;
  }
  if ( v5 )
  {
    XmlReporter::WriteTabbedRawString(v4, a2, L"<ComponentBlockers>\n");
    for ( i = *a3; i != a3[1]; ++i )
    {
      if ( (__int64)(*(_QWORD *)(*i + 64) - *(_QWORD *)(*i + 56)) >> 3 )
      {
        v7 = SleepStudyXmlReporter::WriteBlockers(a1, a2 + 1);
        if ( v7 )
          return v7;
      }
    }
    XmlReporter::WriteTabbedRawString(v4, a2, L"</ComponentBlockers>\n");
  }
  return v7;
}

```

## disassembly

```asm
0x180047d4c  push    rbx
0x180047d4e  push    rbp
0x180047d4f  push    rsi
0x180047d50  push    rdi
0x180047d51  push    r12
0x180047d53  push    r13
0x180047d55  push    r14
0x180047d57  push    r15
0x180047d59  sub     rsp, 28h
0x180047d5d  mov     rbx, [r8]
0x180047d60  lea     rdi, [rcx+10h]
0x180047d64  xor     r15d, r15d
0x180047d67  mov     r14, r8
0x180047d6a  xor     r12d, r12d
0x180047d6d  mov     ebp, edx
0x180047d6f  mov     r13, rcx
0x180047d72  cmp     rbx, [r14+8]
0x180047d76  jz      loc_180047EE3
0x180047d7c  mov     rsi, [rbx]
0x180047d7f  lea     rdi, [r13+10h]
0x180047d83  mov     rcx, rdi; this
0x180047d86  lea     r8, aComponentIndex; "<Component Index=\""
0x180047d8d  mov     edx, ebp; unsigned int
0x180047d8f  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x180047d94  mov     edx, [rsi+248h]; unsigned int
0x180047d9a  mov     rcx, rdi; this
0x180047d9d  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180047da2  cmp     qword ptr [rsi+78h], 0FFFFFFFFFFFFFFFFh
0x180047da7  mov     rcx, rdi; this
0x180047daa  jz      short loc_180047E28
0x180047dac  lea     rdx, aScenarioactive_0; "\" ScenarioActiveTimePercent=\""
0x180047db3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047db8  mov     rcx, rsi; this
0x180047dbb  call    ?GetScenarioActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetScenarioActiveTimePercent(void)
0x180047dc0  addsd   xmm0, cs:__real@3fe0000000000000; X
0x180047dc8  call    floor
0x180047dcd  cvttsd2si rdx, xmm0; unsigned int
0x180047dd2  mov     rcx, rdi; this
0x180047dd5  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180047dda  lea     rdx, aSegmentactivet_0; "\" SegmentActiveTimePercent=\""
0x180047de1  mov     rcx, rdi; this
0x180047de4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047de9  mov     rcx, rsi; this
0x180047dec  call    ?GetSegmentActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetSegmentActiveTimePercent(void)
0x180047df1  addsd   xmm0, cs:__real@3fe0000000000000; X
0x180047df9  call    floor
0x180047dfe  cvttsd2si rdx, xmm0; unsigned int
0x180047e03  mov     rcx, rdi; this
0x180047e06  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180047e0b  lea     rdx, aActivetime_1; "\" ActiveTime=\""
0x180047e12  mov     rcx, rdi; this
0x180047e15  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047e1a  mov     rdx, [rsi+78h]; unsigned __int64
0x180047e1e  mov     rcx, rdi; this
0x180047e21  call    ?WriteInteger64@XmlReporter@@IEAAK_K@Z; XmlReporter::WriteInteger64(unsigned __int64)
0x180047e26  jmp     short loc_180047E52
0x180047e28  lea     rdx, aScenarioactive; "\" ScenarioActiveTimePercent=\"invalid"
0x180047e2f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047e34  lea     rdx, aSegmentactivet; "\" SegmentActiveTimePercent=\"invalid"
0x180047e3b  mov     rcx, rdi; this
0x180047e3e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047e43  lea     rdx, aActivetimeInva; "\" ActiveTime=\"invalid"
0x180047e4a  mov     rcx, rdi; this
0x180047e4d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047e52  lea     rdx, aActivitylevel; "\" ActivityLevel=\""
0x180047e59  mov     rcx, rdi; this
0x180047e5c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047e61  mov     rcx, rsi
0x180047e64  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x180047e69  cmp     eax, 5
0x180047e6c  jl      short loc_180047E73
0x180047e6e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047e73  mov     rcx, rsi
0x180047e76  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x180047e7b  test    eax, eax
0x180047e7d  js      short loc_180047EA4
0x180047e7f  mov     rcx, rsi
0x180047e82  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x180047e87  cmp     eax, 5
0x180047e8a  jge     short loc_180047EA4
0x180047e8c  mov     rcx, rsi
0x180047e8f  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x180047e94  movsxd  rcx, eax
0x180047e97  lea     rdx, ?ActivityLevelNames@@3PAPEAGA; ushort * near * ActivityLevelNames
0x180047e9e  mov     rdx, [rdx+rcx*8]
0x180047ea2  jmp     short loc_180047EAB
0x180047ea4  lea     rdx, aUnrecognized; "unrecognized"
0x180047eab  mov     rcx, rdi; this
0x180047eae  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047eb3  lea     rdx, asc_18009A0D8; "\" />\n"
0x180047eba  mov     rcx, rdi; this
0x180047ebd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180047ec2  mov     rax, [rsi+40h]
0x180047ec6  mov     ecx, 1
0x180047ecb  sub     rax, [rsi+38h]
0x180047ecf  sar     rax, 3
0x180047ed3  test    rax, rax
0x180047ed6  cmovnz  r15d, ecx
0x180047eda  add     rbx, 8
0x180047ede  jmp     loc_180047D72
0x180047ee3  test    r15d, r15d
0x180047ee6  jz      short loc_180047F42
0x180047ee8  lea     r8, aComponentblock_0; "<ComponentBlockers>\n"
0x180047eef  mov     edx, ebp; unsigned int
0x180047ef1  mov     rcx, rdi; this
0x180047ef4  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x180047ef9  mov     rbx, [r14]
0x180047efc  cmp     rbx, [r14+8]
0x180047f00  jz      short loc_180047F31
0x180047f02  mov     r8, [rbx]
0x180047f05  add     r8, 38h ; '8'
0x180047f09  mov     rax, [r8+8]
0x180047f0d  sub     rax, [r8]
0x180047f10  sar     rax, 3
0x180047f14  test    rax, rax
0x180047f17  jz      short loc_180047F2B
0x180047f19  lea     edx, [rbp+1]
0x180047f1c  mov     rcx, r13
0x180047f1f  call    ?WriteBlockers@SleepStudyXmlReporter@@IEAAKKAEBV?$vector@PEAUScenarioBlockerData@@V?$allocator@PEAUScenarioBlockerData@@@std@@@std@@@Z; SleepStudyXmlReporter::WriteBlockers(ulong,std::vector<ScenarioBlockerData *> const &)
0x180047f24  mov     r12d, eax
0x180047f27  test    eax, eax
0x180047f29  jnz     short loc_180047F42
0x180047f2b  add     rbx, 8
0x180047f2f  jmp     short loc_180047EFC
0x180047f31  lea     r8, aComponentblock; "</ComponentBlockers>\n"
0x180047f38  mov     edx, ebp; unsigned int
0x180047f3a  mov     rcx, rdi; this
0x180047f3d  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x180047f42  mov     eax, r12d
0x180047f45  add     rsp, 28h
0x180047f49  pop     r15
0x180047f4b  pop     r14
0x180047f4d  pop     r13
0x180047f4f  pop     r12
0x180047f51  pop     rdi
0x180047f52  pop     rsi
0x180047f53  pop     rbp
0x180047f54  pop     rbx
0x180047f55  retn
```
