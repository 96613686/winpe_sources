# SleepStudyXmlReporter::WriteSearchIndexerData(ulong,ScreenOnTraceData const *)

- ea: `0x18004959c`
- end: `0x1800499e0`
- name: `?WriteSearchIndexerData@SleepStudyXmlReporter@@IEAAXKPEBUScreenOnTraceData@@@Z`
- size: `1092`
- prototype: `void(SleepStudyXmlReporter *__hidden this, unsigned int, const struct ScreenOnTraceData *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d6fc`

## callees

- `0x180009b98`
- `0x18000f730`
- `0x18001107c`
- `0x180012020`
- `0x18004959c`

## string_xrefs

- `0x180049634`: `" ProtocolString="`
- `0x18004961a`: `" ProtocolCount="`

## pseudocode

```c
void __fastcall SleepStudyXmlReporter::WriteSearchIndexerData(
        SleepStudyXmlReporter *this,
        unsigned int a2,
        const struct ScreenOnTraceData *a3)
{
  XmlReporter *v3; // rdi
  __int64 v6; // rbx
  unsigned int v7; // ebp
  const unsigned __int16 *v8; // rdx
  unsigned int *i; // rbx
  __int64 j; // rbx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx

  v3 = (SleepStudyXmlReporter *)((char *)this + 16);
  XmlReporter::WriteTabbedRawString((SleepStudyXmlReporter *)((char *)this + 16), a2, L"<SearchIndexerData>\n");
  v6 = *((_QWORD *)a3 + 207);
  v7 = a2 + 1;
  while ( v6 != *((_QWORD *)a3 + 208) )
  {
    v7 = a2 + 1;
    XmlReporter::WriteTabbedRawString(v3, a2 + 1, L"<Query TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *(_DWORD *)v6);
    XmlReporter::WriteRawString(v3, L"\" MaxCursorsUsed=\"");
    XmlReporter::WriteInteger(v3, *(_DWORD *)(v6 + 4));
    XmlReporter::WriteRawString(v3, L"\" ProtocolCount=\"");
    XmlReporter::WriteInteger(v3, *(_DWORD *)(v6 + 8));
    XmlReporter::WriteRawString(v3, L"\" ProtocolString=\"");
    v8 = (const unsigned __int16 *)(v6 + 16);
    if ( *(_QWORD *)(v6 + 40) > 7u )
      v8 = *(const unsigned __int16 **)v8;
    XmlReporter::WriteRawString(v3, v8);
    XmlReporter::WriteRawString(v3, L"\" />\n");
    v6 += 48;
  }
  if ( *((_DWORD *)a3 + 420) )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<Flush TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 420));
    XmlReporter::WriteRawString(v3, L"\" MaxKeyCount=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 421));
    XmlReporter::WriteRawString(v3, L"\" MaxDocuments=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 422));
    XmlReporter::WriteRawString(v3, L"\" MaxWordList=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 423));
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  for ( i = (unsigned int *)*((_QWORD *)a3 + 212); i != *((unsigned int **)a3 + 213); i += 9 )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<Merge TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *i);
    XmlReporter::WriteRawString(v3, L"\" PreMergeIndiceCount=\"");
    XmlReporter::WriteInteger(v3, i[1]);
    XmlReporter::WriteRawString(v3, L"\" PreMergeLevel=\"");
    XmlReporter::WriteInteger(v3, i[2]);
    XmlReporter::WriteRawString(v3, L"\" PreMergeMinId=\"");
    XmlReporter::WriteInteger(v3, i[3]);
    XmlReporter::WriteRawString(v3, L"\" PreMergeMaxId=\"");
    XmlReporter::WriteInteger(v3, i[4]);
    XmlReporter::WriteRawString(v3, L"\" PostMergeIndiceCount=\"");
    XmlReporter::WriteInteger(v3, i[5]);
    XmlReporter::WriteRawString(v3, L"\" PostMergeLevel=\"");
    XmlReporter::WriteInteger(v3, i[6]);
    XmlReporter::WriteRawString(v3, L"\" PostMergeMinId=\"");
    XmlReporter::WriteInteger(v3, i[7]);
    XmlReporter::WriteRawString(v3, L"\" PostMergeMaxId=\"");
    XmlReporter::WriteInteger(v3, i[8]);
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  if ( *((_DWORD *)a3 + 430) )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<FileSysChange TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 430));
    XmlReporter::WriteRawString(v3, L"\" TotalFATItemsProcessed=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 431));
    XmlReporter::WriteRawString(v3, L"\" TotalNTFSItemsProcessed=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 432));
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  for ( j = *((_QWORD *)a3 + 217); j != *((_QWORD *)a3 + 218); j += 72 )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<IndexingFile TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *(_DWORD *)j);
    XmlReporter::WriteRawString(v3, L"\" IndexingFileAggregationDataMetric=\"");
    v11 = (const unsigned __int16 *)(j + 40);
    if ( *(_QWORD *)(j + 64) > 7u )
      v11 = *(const unsigned __int16 **)v11;
    XmlReporter::WriteString(v3, v11);
    XmlReporter::WriteRawString(v3, L"\" DataTypeCount=\"");
    XmlReporter::WriteInteger(v3, *(_DWORD *)(j + 4));
    XmlReporter::WriteRawString(v3, L"\" DataTypeString=\"");
    v12 = (const unsigned __int16 *)(j + 8);
    if ( *(_QWORD *)(j + 32) > 7u )
      v12 = *(const unsigned __int16 **)v12;
    XmlReporter::WriteString(v3, v12);
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  if ( *((_DWORD *)a3 + 440) )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<EnteringIdle TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 440));
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  if ( *((_DWORD *)a3 + 441) )
  {
    XmlReporter::WriteTabbedRawString(v3, v7, L"<QueryResults TotalNumberOfEvents=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 441));
    XmlReporter::WriteRawString(v3, L"\" TotalResultsRequested=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 442));
    XmlReporter::WriteRawString(v3, L"\" TotalResultsReturned=\"");
    XmlReporter::WriteInteger(v3, *((_DWORD *)a3 + 443));
    XmlReporter::WriteRawString(v3, L"\" />\n");
  }
  XmlReporter::WriteTabbedRawString(v3, a2, L"</SearchIndexerData>\n");
}

```

## disassembly

```asm
0x18004959c  push    rbx
0x18004959e  push    rbp
0x18004959f  push    rsi
0x1800495a0  push    rdi
0x1800495a1  push    r14
0x1800495a3  push    r15
0x1800495a5  sub     rsp, 28h
0x1800495a9  lea     rdi, [rcx+10h]
0x1800495ad  mov     rsi, r8
0x1800495b0  mov     rcx, rdi; this
0x1800495b3  lea     r8, aSearchindexerd_1; "<SearchIndexerData>\n"
0x1800495ba  mov     r14d, edx
0x1800495bd  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x1800495c2  mov     rbx, [rsi+678h]
0x1800495c9  lea     ebp, [r14+1]
0x1800495cd  lea     r15, asc_18009A0D8; "\" />\n"
0x1800495d4  cmp     rbx, [rsi+680h]
0x1800495db  jz      loc_18004966D
0x1800495e1  lea     ebp, [r14+1]
0x1800495e5  mov     rcx, rdi; this
0x1800495e8  mov     edx, ebp; unsigned int
0x1800495ea  lea     r8, aQueryTotalnumb; "<Query TotalNumberOfEvents=\""
0x1800495f1  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x1800495f6  mov     edx, [rbx]; unsigned int
0x1800495f8  mov     rcx, rdi; this
0x1800495fb  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049600  lea     rdx, aMaxcursorsused_0; "\" MaxCursorsUsed=\""
0x180049607  mov     rcx, rdi; this
0x18004960a  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004960f  mov     edx, [rbx+4]; unsigned int
0x180049612  mov     rcx, rdi; this
0x180049615  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004961a  lea     rdx, aProtocolcount; "\" ProtocolCount=\""
0x180049621  mov     rcx, rdi; this
0x180049624  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049629  mov     edx, [rbx+8]; unsigned int
0x18004962c  mov     rcx, rdi; this
0x18004962f  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049634  lea     rdx, aProtocolstring; "\" ProtocolString=\""
0x18004963b  mov     rcx, rdi; this
0x18004963e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049643  cmp     qword ptr [rbx+28h], 7
0x180049648  lea     rdx, [rbx+10h]
0x18004964c  jbe     short loc_180049651
0x18004964e  mov     rdx, [rdx]; unsigned __int16 *
0x180049651  mov     rcx, rdi; this
0x180049654  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049659  mov     rdx, r15; unsigned __int16 *
0x18004965c  mov     rcx, rdi; this
0x18004965f  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049664  add     rbx, 30h ; '0'
0x180049668  jmp     loc_1800495D4
0x18004966d  cmp     dword ptr [rsi+690h], 0
0x180049674  jbe     loc_1800496FB
0x18004967a  lea     r8, aFlushTotalnumb; "<Flush TotalNumberOfEvents=\""
0x180049681  mov     edx, ebp; unsigned int
0x180049683  mov     rcx, rdi; this
0x180049686  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004968b  mov     edx, [rsi+690h]; unsigned int
0x180049691  mov     rcx, rdi; this
0x180049694  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049699  lea     rdx, aMaxkeycount_0; "\" MaxKeyCount=\""
0x1800496a0  mov     rcx, rdi; this
0x1800496a3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800496a8  mov     edx, [rsi+694h]; unsigned int
0x1800496ae  mov     rcx, rdi; this
0x1800496b1  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800496b6  lea     rdx, aMaxdocuments_0; "\" MaxDocuments=\""
0x1800496bd  mov     rcx, rdi; this
0x1800496c0  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800496c5  mov     edx, [rsi+698h]; unsigned int
0x1800496cb  mov     rcx, rdi; this
0x1800496ce  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800496d3  lea     rdx, aMaxwordlist_0; "\" MaxWordList=\""
0x1800496da  mov     rcx, rdi; this
0x1800496dd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800496e2  mov     edx, [rsi+69Ch]; unsigned int
0x1800496e8  mov     rcx, rdi; this
0x1800496eb  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800496f0  mov     rdx, r15; unsigned __int16 *
0x1800496f3  mov     rcx, rdi; this
0x1800496f6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800496fb  mov     rbx, [rsi+6A0h]
0x180049702  cmp     rbx, [rsi+6A8h]
0x180049709  jz      loc_18004980E
0x18004970f  lea     r8, aMergeTotalnumb; "<Merge TotalNumberOfEvents=\""
0x180049716  mov     edx, ebp; unsigned int
0x180049718  mov     rcx, rdi; this
0x18004971b  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x180049720  mov     edx, [rbx]; unsigned int
0x180049722  mov     rcx, rdi; this
0x180049725  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004972a  lea     rdx, aPremergeindice_0; "\" PreMergeIndiceCount=\""
0x180049731  mov     rcx, rdi; this
0x180049734  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049739  mov     edx, [rbx+4]; unsigned int
0x18004973c  mov     rcx, rdi; this
0x18004973f  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049744  lea     rdx, aPremergelevel_0; "\" PreMergeLevel=\""
0x18004974b  mov     rcx, rdi; this
0x18004974e  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049753  mov     edx, [rbx+8]; unsigned int
0x180049756  mov     rcx, rdi; this
0x180049759  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004975e  lea     rdx, aPremergeminid; "\" PreMergeMinId=\""
0x180049765  mov     rcx, rdi; this
0x180049768  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004976d  mov     edx, [rbx+0Ch]; unsigned int
0x180049770  mov     rcx, rdi; this
0x180049773  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049778  lea     rdx, aPremergemaxid_0; "\" PreMergeMaxId=\""
0x18004977f  mov     rcx, rdi; this
0x180049782  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049787  mov     edx, [rbx+10h]; unsigned int
0x18004978a  mov     rcx, rdi; this
0x18004978d  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049792  lea     rdx, aPostmergeindic; "\" PostMergeIndiceCount=\""
0x180049799  mov     rcx, rdi; this
0x18004979c  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800497a1  mov     edx, [rbx+14h]; unsigned int
0x1800497a4  mov     rcx, rdi; this
0x1800497a7  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800497ac  lea     rdx, aPostmergelevel_0; "\" PostMergeLevel=\""
0x1800497b3  mov     rcx, rdi; this
0x1800497b6  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800497bb  mov     edx, [rbx+18h]; unsigned int
0x1800497be  mov     rcx, rdi; this
0x1800497c1  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800497c6  lea     rdx, aPostmergeminid; "\" PostMergeMinId=\""
0x1800497cd  mov     rcx, rdi; this
0x1800497d0  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800497d5  mov     edx, [rbx+1Ch]; unsigned int
0x1800497d8  mov     rcx, rdi; this
0x1800497db  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800497e0  lea     rdx, aPostmergemaxid_0; "\" PostMergeMaxId=\""
0x1800497e7  mov     rcx, rdi; this
0x1800497ea  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800497ef  mov     edx, [rbx+20h]; unsigned int
0x1800497f2  mov     rcx, rdi; this
0x1800497f5  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800497fa  mov     rdx, r15; unsigned __int16 *
0x1800497fd  mov     rcx, rdi; this
0x180049800  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049805  add     rbx, 24h ; '$'
0x180049809  jmp     loc_180049702
0x18004980e  cmp     dword ptr [rsi+6B8h], 0
0x180049815  jbe     short loc_18004987B
0x180049817  lea     r8, aFilesyschangeT; "<FileSysChange TotalNumberOfEvents=\""
0x18004981e  mov     edx, ebp; unsigned int
0x180049820  mov     rcx, rdi; this
0x180049823  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x180049828  mov     edx, [rsi+6B8h]; unsigned int
0x18004982e  mov     rcx, rdi; this
0x180049831  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049836  lea     rdx, aTotalfatitemsp; "\" TotalFATItemsProcessed=\""
0x18004983d  mov     rcx, rdi; this
0x180049840  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049845  mov     edx, [rsi+6BCh]; unsigned int
0x18004984b  mov     rcx, rdi; this
0x18004984e  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049853  lea     rdx, aTotalntfsitems; "\" TotalNTFSItemsProcessed=\""
0x18004985a  mov     rcx, rdi; this
0x18004985d  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049862  mov     edx, [rsi+6C0h]; unsigned int
0x180049868  mov     rcx, rdi; this
0x18004986b  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x180049870  mov     rdx, r15; unsigned __int16 *
0x180049873  mov     rcx, rdi; this
0x180049876  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004987b  mov     rbx, [rsi+6C8h]
0x180049882  cmp     rbx, [rsi+6D0h]
0x180049889  jz      loc_180049922
0x18004988f  lea     r8, aIndexingfileTo; "<IndexingFile TotalNumberOfEvents=\""
0x180049896  mov     edx, ebp; unsigned int
0x180049898  mov     rcx, rdi; this
0x18004989b  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x1800498a0  mov     edx, [rbx]; unsigned int
0x1800498a2  mov     rcx, rdi; this
0x1800498a5  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800498aa  lea     rdx, aIndexingfileag_0; "\" IndexingFileAggregationDataMetric=\""
0x1800498b1  mov     rcx, rdi; this
0x1800498b4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800498b9  cmp     qword ptr [rbx+40h], 7
0x1800498be  lea     rdx, [rbx+28h]
0x1800498c2  jbe     short loc_1800498C7
0x1800498c4  mov     rdx, [rdx]; unsigned __int16 *
0x1800498c7  mov     rcx, rdi; this
0x1800498ca  call    ?WriteString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteString(ushort const *)
0x1800498cf  lea     rdx, aDatatypecount; "\" DataTypeCount=\""
0x1800498d6  mov     rcx, rdi; this
0x1800498d9  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800498de  mov     edx, [rbx+4]; unsigned int
0x1800498e1  mov     rcx, rdi; this
0x1800498e4  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800498e9  lea     rdx, aDatatypestring; "\" DataTypeString=\""
0x1800498f0  mov     rcx, rdi; this
0x1800498f3  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800498f8  cmp     qword ptr [rbx+20h], 7
0x1800498fd  lea     rdx, [rbx+8]
0x180049901  jbe     short loc_180049906
0x180049903  mov     rdx, [rdx]; unsigned __int16 *
0x180049906  mov     rcx, rdi; this
0x180049909  call    ?WriteString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteString(ushort const *)
0x18004990e  mov     rdx, r15; unsigned __int16 *
0x180049911  mov     rcx, rdi; this
0x180049914  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049919  add     rbx, 48h ; 'H'
0x18004991d  jmp     loc_180049882
0x180049922  cmp     dword ptr [rsi+6E0h], 0
0x180049929  jbe     short loc_180049955
0x18004992b  lea     r8, aEnteringidleTo; "<EnteringIdle TotalNumberOfEvents=\""
0x180049932  mov     edx, ebp; unsigned int
0x180049934  mov     rcx, rdi; this
0x180049937  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004993c  mov     edx, [rsi+6E0h]; unsigned int
0x180049942  mov     rcx, rdi; this
0x180049945  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004994a  mov     rdx, r15; unsigned __int16 *
0x18004994d  mov     rcx, rdi; this
0x180049950  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x180049955  cmp     dword ptr [rsi+6E4h], 0
0x18004995c  jbe     short loc_1800499C2
0x18004995e  lea     r8, aQueryresultsTo; "<QueryResults TotalNumberOfEvents=\""
0x180049965  mov     edx, ebp; unsigned int
0x180049967  mov     rcx, rdi; this
0x18004996a  call    ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
0x18004996f  mov     edx, [rsi+6E4h]; unsigned int
0x180049975  mov     rcx, rdi; this
0x180049978  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004997d  lea     rdx, aTotalresultsre_2; "\" TotalResultsRequested=\""
0x180049984  mov     rcx, rdi; this
0x180049987  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x18004998c  mov     edx, [rsi+6E8h]; unsigned int
0x180049992  mov     rcx, rdi; this
0x180049995  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x18004999a  lea     rdx, aTotalresultsre_0; "\" TotalResultsReturned=\""
0x1800499a1  mov     rcx, rdi; this
0x1800499a4  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800499a9  mov     edx, [rsi+6ECh]; unsigned int
0x1800499af  mov     rcx, rdi; this
0x1800499b2  call    ?WriteInteger@XmlReporter@@IEAAKK@Z; XmlReporter::WriteInteger(ulong)
0x1800499b7  mov     rdx, r15; unsigned __int16 *
0x1800499ba  mov     rcx, rdi; this
0x1800499bd  call    ?WriteRawString@XmlReporter@@IEAAKPEBG@Z; XmlReporter::WriteRawString(ushort const *)
0x1800499c2  lea     r8, aSearchindexerd; "</SearchIndexerData>\n"
0x1800499c9  mov     edx, r14d; unsigned int
0x1800499cc  mov     rcx, rdi; this
0x1800499cf  add     rsp, 28h
0x1800499d3  pop     r15
0x1800499d5  pop     r14
0x1800499d7  pop     rdi
0x1800499d8  pop     rsi
0x1800499d9  pop     rbp
0x1800499da  pop     rbx
0x1800499db  jmp     ?WriteTabbedRawString@XmlReporter@@IEAAKKPEBG@Z; XmlReporter::WriteTabbedRawString(ulong,ushort const *)
```
