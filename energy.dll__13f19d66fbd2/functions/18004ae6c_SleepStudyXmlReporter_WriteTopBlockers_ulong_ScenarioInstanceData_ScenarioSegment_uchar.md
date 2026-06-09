# SleepStudyXmlReporter::WriteTopBlockers(ulong,ScenarioInstanceData *,ScenarioSegment,uchar)

- ea: `0x18004ae6c`
- end: `0x18004b12a`
- name: `?WriteTopBlockers@SleepStudyXmlReporter@@IEAAKKPEAUScenarioInstanceData@@W4ScenarioSegment@@E@Z`
- size: `702`
- prototype: `unsigned int __high(unsigned int, struct ScenarioInstanceData *, enum ScenarioSegment, unsigned __int8)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800851d4`
- `0x180085f4c`

## callees

- `0x180008740`
- `0x180009b5c`
- `0x18000f730`
- `0x18001107c`
- `0x1800110c4`
- `0x180011948`
- `0x180012020`
- `0x18001292c`
- `0x180012a98`
- `0x18001464c`
- `0x18001c8cc`
- `0x18004ae6c`
- `0x18004d8c0`
- `0x180084198`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004af1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004af1f`

## pseudocode

```c
__int64 __fastcall SleepStudyXmlReporter::WriteTopBlockers(__int64 a1, unsigned int a2, __int64 a3, int a4, char a5)
{
  XmlReporter *v5; // rsi
  int v8; // ebp
  int v9; // r12d
  _QWORD *i; // rbx
  __int64 v12; // rdi
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  double ScenarioActiveTimePercent; // xmm0_8
  double v16; // xmm0_8
  double SegmentActiveTimePercent; // xmm0_8
  double v18; // xmm0_8
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rdx
  _BYTE v22[88]; // [rsp+20h] [rbp-58h] BYREF

  v5 = (XmlReporter *)(a1 + 16);
  v8 = 0;
  v9 = a4;
  XmlReporter::WriteTabbedRawString((XmlReporter *)(a1 + 16), a2, L"<TopBlockers>\n");
  for ( i = *(_QWORD **)(a3 + 560); i != *(_QWORD **)(a3 + 568) && v8 != 5; ++i )
  {
    v12 = *i;
    if ( (unsigned int)BlockerData::GetSegment(*i) == v9 )
    {
      if ( *(_DWORD *)(v12 + 40) == 7 || *(_DWORD *)(v12 + 40) == 5 )
        goto LABEL_6;
      if ( *(_DWORD *)(v12 + 40) != 1 || a5 || !*(_BYTE *)(a3 + 128) )
        goto LABEL_14;
      v13 = (_QWORD *)(v12 + 8);
      if ( *(_QWORD *)(v12 + 32) > 7u )
        v13 = (_QWORD *)*v13;
      if ( !(unsigned int)_o__wcsnicmp(v13, L"Unregistered Device", 19) )
      {
LABEL_6:
        --v8;
      }
      else
      {
LABEL_14:
        XmlReporter::WriteTabbedRawString(v5, a2 + 1, L"<TopBlocker Name=\"");
        v14 = (_QWORD *)std::wstring::wstring((__int64)v22, (_QWORD *)(v12 + 8));
        XmlReporter::WriteStlString(v5, v14);
        if ( *(_QWORD *)(v12 + 120) == -1 )
        {
          XmlReporter::WriteRawString(v5, L"\" ScenarioActiveTimePercent=\"invalid");
          XmlReporter::WriteRawString(v5, L"\" SegmentActiveTimePercent=\"invalid");
          XmlReporter::WriteRawString(v5, L"\" ActiveTime=\"invalid");
        }
        else
        {
          XmlReporter::WriteRawString(v5, L"\" ScenarioActiveTimePercent=\"");
          ScenarioActiveTimePercent = BlockerData::GetScenarioActiveTimePercent((BlockerData *)v12);
          v16 = floor(ScenarioActiveTimePercent + 0.5);
          XmlReporter::WriteInteger(v5, (int)v16);
          XmlReporter::WriteRawString(v5, L"\" SegmentActiveTimePercent=\"");
          SegmentActiveTimePercent = BlockerData::GetSegmentActiveTimePercent((BlockerData *)v12);
          v18 = floor(SegmentActiveTimePercent + 0.5);
          XmlReporter::WriteInteger(v5, (int)v18);
          XmlReporter::WriteRawString(v5, L"\" ActiveTime=\"");
          XmlReporter::WriteInteger64(v5, *(_QWORD *)(v12 + 120));
        }
        XmlReporter::WriteRawString(v5, L"\" ActivityLevel=\"");
        if ( (int)BlockerData::GetActivityLevel(v12) >= 5 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)BlockerData::GetActivityLevel(v12) < 0 || (int)BlockerData::GetActivityLevel(v12) >= 5 )
          v19 = L"unrecognized";
        else
          v19 = (&ActivityLevelNames)[(int)BlockerData::GetActivityLevel(v12)];
        XmlReporter::WriteRawString(v5, v19);
        XmlReporter::WriteRawString(v5, L"\" Type=\"");
        if ( *(int *)(v12 + 40) >= 10 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( *(_DWORD *)(v12 + 40) > 9u )
          v20 = L"unrecognized";
        else
          v20 = (const unsigned __int16 *)(&BlockerTypeNames)[*(int *)(v12 + 40)];
        XmlReporter::WriteRawString(v5, v20);
        XmlReporter::WriteRawString(v5, L"\" Id=\"");
        SleepStudyXmlReporter::WriteBlockerId(a1, *(_QWORD *)(v12 + 44));
        XmlReporter::WriteRawString(v5, L"\">\n");
        XmlReporter::WriteTabbedRawString(v5, a2 + 1, L"</TopBlocker>\n");
        v9 = a4;
      }
    }
    ++v8;
  }
  XmlReporter::WriteTabbedRawString(v5, a2, L"</TopBlockers>\n");
  return 0;
}

```

## disassembly

```asm
0x18004ae6c  mov     [rsp+arg_8], rbx
0x18004ae71  mov     [rsp+arg_18], r9d
0x18004ae76  push    rbp
0x18004ae77  push    rsi
0x18004ae78  push    rdi
0x18004ae79  push    r12
0x18004ae7b  push    r13
0x18004ae7d  push    r14
0x18004ae7f  push    r15
0x18004ae81  sub     rsp, 40h
0x18004ae85  lea     rsi, [rcx+10h]
0x18004ae89  mov     r14, r8
0x18004ae8c  mov     r13, rcx
0x18004ae8f  lea     r8, aTopblockers_0; "<TopBlockers>\n"
0x18004ae96  mov     rcx, rsi; this
0x18004ae99  xor     ebp, ebp
0x18004ae9b  mov     r12d, r9d
0x18004ae9e  mov     r15d, edx
0x18004aea1  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004aea6  mov     rbx, [r14+230h]
0x18004aead  cmp     rbx, [r14+238h]
0x18004aeb4  jz      loc_18004B0FE
0x18004aeba  cmp     ebp, 5
0x18004aebd  jz      loc_18004B0FE
0x18004aec3  mov     rdi, [rbx]
0x18004aec6  mov     rcx, rdi
0x18004aec9  call    ?GetSegment@BlockerData@@QEBA?AW4ScenarioSegment@@XZ; BlockerData::GetSegment(void)
0x18004aece  cmp     eax, r12d
0x18004aed1  jnz     loc_18004B0F3
0x18004aed7  cmp     dword ptr [rdi+28h], 7
0x18004aedb  jnz     short loc_18004AEE4
0x18004aedd  dec     ebp
0x18004aedf  jmp     loc_18004B0F3
0x18004aee4  cmp     dword ptr [rdi+28h], 5
0x18004aee8  jz      short loc_18004AEDD
0x18004aeea  cmp     dword ptr [rdi+28h], 1
0x18004aeee  jnz     short loc_18004AF29
0x18004aef0  cmp     [rsp+78h+arg_20], 0
0x18004aef8  jnz     short loc_18004AF29
0x18004aefa  cmp     byte ptr [r14+80h], 0
0x18004af02  jz      short loc_18004AF29
0x18004af04  cmp     qword ptr [rdi+20h], 7
0x18004af09  lea     rcx, [rdi+8]
0x18004af0d  jbe     short loc_18004AF12
0x18004af0f  mov     rcx, [rcx]
0x18004af12  mov     r8d, 13h
0x18004af18  lea     rdx, aUnregisteredDe; "Unregistered Device"
0x18004af1f  call    cs:__imp__o__wcsnicmp
0x18004af25  test    eax, eax
0x18004af27  jz      short loc_18004AEDD
0x18004af29  lea     r8, aTopblockerName; "<TopBlocker Name=\""
0x18004af30  mov     rcx, rsi; this
0x18004af33  lea     edx, [r15+1]; unsigned int
0x18004af37  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004af3c  lea     rdx, [rdi+8]
0x18004af40  lea     rcx, [rsp+78h+var_58]
0x18004af45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004af4a  mov     rdx, rax
0x18004af4d  mov     rcx, rsi
0x18004af50  call    ?WriteStlString@XmlReporter@@IEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; XmlReporter::WriteStlString(std::wstring)
0x18004af55  cmp     qword ptr [rdi+78h], 0FFFFFFFFFFFFFFFFh
0x18004af5a  mov     rcx, rsi; this
0x18004af5d  jz      short loc_18004AFDB
0x18004af5f  lea     rdx, aScenarioactive_0; "\" ScenarioActiveTimePercent=\""
0x18004af66  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004af6b  mov     rcx, rdi; this
0x18004af6e  call    ?GetScenarioActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetScenarioActiveTimePercent(void)
0x18004af73  addsd   xmm0, cs:__real@3fe0000000000000; X
0x18004af7b  call    floor
0x18004af80  cvttsd2si rdx, xmm0; unsigned int
0x18004af85  mov     rcx, rsi; this
0x18004af88  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004af8d  lea     rdx, aSegmentactivet_0; "\" SegmentActiveTimePercent=\""
0x18004af94  mov     rcx, rsi; this
0x18004af97  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004af9c  mov     rcx, rdi; this
0x18004af9f  call    ?GetSegmentActiveTimePercent@BlockerData@@QEBANXZ; BlockerData::GetSegmentActiveTimePercent(void)
0x18004afa4  addsd   xmm0, cs:__real@3fe0000000000000; X
0x18004afac  call    floor
0x18004afb1  cvttsd2si rdx, xmm0; unsigned int
0x18004afb6  mov     rcx, rsi; this
0x18004afb9  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004afbe  lea     rdx, aActivetime_1; "\" ActiveTime=\""
0x18004afc5  mov     rcx, rsi; this
0x18004afc8  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004afcd  mov     rdx, [rdi+78h]; unsigned __int64
0x18004afd1  mov     rcx, rsi; this
0x18004afd4  call    ?WriteInteger64@XmlReporter@@IEAAK_K@Z; XmlReporter::WriteInteger64(unsigned __int64)
0x18004afd9  jmp     short loc_18004B005
0x18004afdb  lea     rdx, aScenarioactive; "\" ScenarioActiveTimePercent=\"invalid"
0x18004afe2  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004afe7  lea     rdx, aSegmentactivet; "\" SegmentActiveTimePercent=\"invalid"
0x18004afee  mov     rcx, rsi; this
0x18004aff1  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004aff6  lea     rdx, aActivetimeInva; "\" ActiveTime=\"invalid"
0x18004affd  mov     rcx, rsi; this
0x18004b000  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b005  lea     rdx, aActivitylevel; "\" ActivityLevel=\""
0x18004b00c  mov     rcx, rsi; this
0x18004b00f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b014  mov     rcx, rdi
0x18004b017  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x18004b01c  cmp     eax, 5
0x18004b01f  jl      short loc_18004B026
0x18004b021  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004b026  mov     rcx, rdi
0x18004b029  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x18004b02e  test    eax, eax
0x18004b030  js      short loc_18004B05B
0x18004b032  mov     rcx, rdi
0x18004b035  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x18004b03a  cmp     eax, 5
0x18004b03d  jge     short loc_18004B05B
0x18004b03f  mov     rcx, rdi
0x18004b042  call    ?GetActivityLevel@BlockerData@@QEBA?AW4ActivityLevel@@XZ; BlockerData::GetActivityLevel(void)
0x18004b047  movsxd  rcx, eax
0x18004b04a  lea     rax, __ImageBase
0x18004b051  mov     rdx, ds:rva ?ActivityLevelNames@@3PAPEAGA[rax+rcx*8]; ushort * near * ActivityLevelNames ...
0x18004b059  jmp     short loc_18004B062
0x18004b05b  lea     rdx, aUnrecognized; "unrecognized"
0x18004b062  mov     rcx, rsi; this
0x18004b065  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b06a  lea     rdx, aType_0; "\" Type=\""
0x18004b071  mov     rcx, rsi; this
0x18004b074  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b079  cmp     dword ptr [rdi+28h], 0Ah
0x18004b07d  jl      short loc_18004B084
0x18004b07f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004b084  cmp     dword ptr [rdi+28h], 9
0x18004b088  ja      short loc_18004B09F
0x18004b08a  movsxd  rax, dword ptr [rdi+28h]
0x18004b08e  lea     rcx, __ImageBase
0x18004b095  mov     rdx, ds:rva ?BlockerTypeNames@@3PAPEAGA[rcx+rax*8]; ushort * near * BlockerTypeNames ...
0x18004b09d  jmp     short loc_18004B0A6
0x18004b09f  lea     rdx, aUnrecognized; "unrecognized"
0x18004b0a6  mov     rcx, rsi; this
0x18004b0a9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b0ae  lea     rdx, aId_6; "\" Id=\""
0x18004b0b5  mov     rcx, rsi; this
0x18004b0b8  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b0bd  mov     rdx, [rdi+2Ch]
0x18004b0c1  mov     rcx, r13
0x18004b0c4  call    ?WriteBlockerId@SleepStudyXmlReporter@@IEAAKUBlockerDataId@@@Z; SleepStudyXmlReporter::WriteBlockerId(BlockerDataId)
0x18004b0c9  lea     rdx, asc_180099F68; "\">\n"
0x18004b0d0  mov     rcx, rsi; this
0x18004b0d3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004b0d8  lea     r8, aTopblocker; "</TopBlocker>\n"
0x18004b0df  mov     rcx, rsi; this
0x18004b0e2  lea     edx, [r15+1]; unsigned int
0x18004b0e6  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004b0eb  mov     r12d, [rsp+78h+arg_18]
0x18004b0f3  add     rbx, 8
0x18004b0f7  inc     ebp
0x18004b0f9  jmp     loc_18004AEAD
0x18004b0fe  lea     r8, aTopblockers; "</TopBlockers>\n"
0x18004b105  mov     edx, r15d; unsigned int
0x18004b108  mov     rcx, rsi; this
0x18004b10b  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004b110  mov     rbx, [rsp+78h+arg_8]
0x18004b118  xor     eax, eax
0x18004b11a  add     rsp, 40h
0x18004b11e  pop     r15
0x18004b120  pop     r14
0x18004b122  pop     r13
0x18004b124  pop     r12
0x18004b126  pop     rdi
0x18004b127  pop     rsi
0x18004b128  pop     rbp
0x18004b129  retn
```
