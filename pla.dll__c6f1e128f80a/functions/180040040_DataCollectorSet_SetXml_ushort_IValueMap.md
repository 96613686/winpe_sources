# DataCollectorSet::SetXml(ushort *,IValueMap * *)

- ea: `0x180040040`
- end: `0x18004083a`
- name: `?SetXml@DataCollectorSet@@UEAAJPEAGPEAPEAUIValueMap@@@Z`
- size: `2042`
- prototype: `void __noreturn(DataCollectorSet *__hidden this, unsigned __int16 *, struct IValueMap **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x180040040`
- `0x180040840`
- `0x180040890`
- `0x18004fa78`
- `0x18005179c`
- `0x1800dd804`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004021d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004021d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004011d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004011d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800402f3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800402f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004027b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004027b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004034a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18004034a`

## string_xrefs

- `0x1800400de`: `DataCollectorSet::SetXml`
- `0x1800401bb`: `DataCollectorSet::SetXml`
- `0x180040482`: `DataCollectorSet::SetXml`
- `0x1800407f2`: `DataCollectorSet::SetXml`

## pseudocode

```c
void __fastcall __noreturn DataCollectorSet::SetXml(
        DataCollectorSet *this,
        unsigned __int16 *a2,
        struct IValueMap **a3)
{
  int v3; // eax
  struct IValueMap *v6; // [rsp+70h] [rbp-90h] BYREF
  __int64 v7; // [rsp+78h] [rbp-88h]
  struct IXMLDOMNode *v8[4]; // [rsp+80h] [rbp-80h] BYREF

  v3 = *((_DWORD *)this + 14);
  v8[1] = 0;
  v8[0] = 0;
  v6 = 0;
  v8[3] = 0;
  LODWORD(v7) = v3;
  v8[2] = (struct IXMLDOMNode *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_METHOD, 3, (__int64)"DataCollectorSet::SetXml");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  PlaiCreateXmlFromString(a2, (struct IXMLDOMElement **)v8, &v6);
}

```

## disassembly

```asm
0x180040040  mov     [rsp-8+arg_18], rbx
0x180040045  push    rbp
0x180040046  push    rsi
0x180040047  push    rdi
0x180040048  push    r12
0x18004004a  push    r13
0x18004004c  push    r14
0x18004004e  push    r15
0x180040050  lea     rbp, [rsp-3B0h]
0x180040058  sub     rsp, 4B0h
0x18004005f  mov     rax, cs:__security_cookie
0x180040066  xor     rax, rsp
0x180040069  mov     [rbp+3E0h+var_40], rax
0x180040070  mov     eax, [rcx+38h]
0x180040073  xor     r14d, r14d
0x180040076  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004007d  mov     rsi, r8
0x180040080  mov     rbx, rdx
0x180040083  mov     [rbp+3E0h+var_458], r14
0x180040087  mov     rdi, rcx
0x18004008a  mov     [rbp+3E0h+var_460], r14
0x18004008e  lea     r15d, [r14+4]
0x180040092  mov     [rsp+4E0h+var_470], r14
0x180040097  lea     r12d, [r14+19h]
0x18004009b  mov     [rbp+3E0h+bstrString], r14
0x18004009f  mov     dword ptr [rsp+4E0h+var_468], eax
0x1800400a3  mov     [rbp+3E0h+var_450], rcx
0x1800400a7  jz      short loc_180040113
0x1800400a9  mov     rdx, 4000000000000400h
0x1800400b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800400ba  jz      short loc_180040113
0x1800400bc  mov     rax, cs:qword_180169748
0x1800400c3  and     rax, rdx
0x1800400c6  cmp     cs:qword_180169748, rax
0x1800400cd  jnz     short loc_180040113
0x1800400cf  mov     [rsp+4E0h+var_4A0], r15
0x1800400d4  lea     rax, [rsp+4E0h+var_468]
0x1800400d9  mov     [rsp+4E0h+var_4A8], rax
0x1800400de  lea     r9, aDatacollectors_62; "DataCollectorSet::SetXml"
0x1800400e5  lea     rax, [rbp+3E0h+var_450]
0x1800400e9  mov     [rsp+4E0h+var_4B0], 8
0x1800400f2  mov     [rsp+4E0h+var_4B8], rax
0x1800400f7  lea     r8d, [r14+3]
0x1800400fb  lea     rdx, PLA_EVENT_METHOD
0x180040102  mov     [rsp+4E0h+var_4C0], r12
0x180040107  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004010e  call    EventingWriteEvent
0x180040113  cmp     [rdi+8], r14d
0x180040117  jz      short loc_180040123
0x180040119  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004011d  call    cs:__imp_EnterCriticalSection
0x180040123  lea     r8, [rsp+4E0h+var_470]; struct IValueMap **
0x180040128  mov     rcx, rbx; unsigned __int16 *
0x18004012b  lea     rdx, [rbp+3E0h+var_460]; struct IXMLDOMElement **
0x18004012f  call    ?PlaiCreateXmlFromString@@YAJPEAGPEAPEAUIXMLDOMElement@@PEAPEAUIValueMap@@@Z; PlaiCreateXmlFromString(ushort *,IXMLDOMElement * *,IValueMap * *)
0x180040134  mov     r13, [rsp+4E0h+var_470]
0x180040139  mov     ebx, eax
0x18004013b  test    eax, eax
0x18004013d  jns     loc_1800402AD
0x180040143  xor     esi, esi
0x180040145  mov     dword ptr [rsp+4E0h+var_470], eax
0x180040149  cmp     dword ptr cs:xmmword_180169738, esi
0x18004014f  mov     dword ptr [rsp+4E0h+var_468], esi
0x180040153  jz      loc_180040214
0x180040159  mov     rdx, 4000000000000800h; unsigned __int64
0x180040163  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004016a  jz      loc_180040214
0x180040170  mov     rax, cs:qword_180169748
0x180040177  and     rax, rdx
0x18004017a  cmp     cs:qword_180169748, rax
0x180040181  jnz     loc_180040214
0x180040187  lea     rcx, [rbp+3E0h+var_440]; unsigned __int16 *
0x18004018b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180040190  lea     rcx, [rbp+3E0h+var_440]
0x180040194  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040198  inc     rax
0x18004019b  cmp     [rcx+rax*2], si
0x18004019f  jnz     short loc_180040198
0x1800401a1  lea     ecx, [rax+rax]
0x1800401a4  lea     rax, [rbp+3E0h+var_440]
0x1800401a8  add     rcx, 2
0x1800401ac  mov     [rsp+4E0h+var_480], rcx
0x1800401b1  lea     r9, [rsp+4E0h+var_470]
0x1800401b6  mov     [rsp+4E0h+var_488], rax
0x1800401bb  lea     rax, aDatacollectors_62; "DataCollectorSet::SetXml"
0x1800401c2  mov     [rsp+4E0h+var_490], r12
0x1800401c7  mov     r12d, 1
0x1800401cd  mov     [rsp+4E0h+var_498], rax
0x1800401d2  lea     rax, [rsp+4E0h+var_468]
0x1800401d7  mov     [rsp+4E0h+var_4A0], r15
0x1800401dc  lea     r15, qword_180147320
0x1800401e3  mov     [rsp+4E0h+var_4A8], rax
0x1800401e8  mov     [rsp+4E0h+var_4B0], r12
0x1800401ed  mov     [rsp+4E0h+var_4B8], r15
0x1800401f2  mov     [rsp+4E0h+var_4C0], 4
0x1800401fb  mov     r8d, 5
0x180040201  lea     rdx, PLA_EVENT_ERROR
0x180040208  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004020f  call    EventingWriteEvent
0x180040214  cmp     [rdi+8], esi
0x180040217  jz      short loc_180040223
0x180040219  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004021d  call    cs:__imp_LeaveCriticalSection
0x180040223  mov     rcx, r14; bstrString
0x180040226  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18004022b  mov     rcx, [rbp+3E0h+var_460]
0x18004022f  test    rcx, rcx
0x180040232  jz      short loc_180040244
0x180040234  mov     rax, [rcx]
0x180040237  mov     rax, [rax+10h]
0x18004023b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040240  mov     [rbp+3E0h+var_460], rsi
0x180040244  test    r13, r13
0x180040247  jz      short loc_180040259
0x180040249  mov     rax, [r13+0]
0x18004024d  mov     rcx, r13
0x180040250  mov     rax, [rax+10h]
0x180040254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040259  mov     rcx, [rbp+3E0h+var_458]
0x18004025d  test    rcx, rcx
0x180040260  jz      short loc_180040272
0x180040262  mov     rax, [rcx]
0x180040265  mov     rax, [rax+10h]
0x180040269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004026e  mov     [rbp+3E0h+var_458], rsi
0x180040272  mov     rcx, [rbp+3E0h+bstrString]; bstrString
0x180040276  test    rcx, rcx
0x180040279  jz      short loc_180040281
0x18004027b  call    cs:__imp_SysFreeString
0x180040281  mov     eax, ebx
0x180040283  mov     rcx, [rbp+3E0h+var_40]
0x18004028a  xor     rcx, rsp; StackCookie
0x18004028d  call    __security_check_cookie
0x180040292  mov     rbx, [rsp+4E0h+arg_18]
0x18004029a  add     rsp, 4B0h
0x1800402a1  pop     r15
0x1800402a3  pop     r14
0x1800402a5  pop     r13
0x1800402a7  pop     r12
0x1800402a9  pop     rdi
0x1800402aa  pop     rsi
0x1800402ab  pop     rbp
0x1800402ac  retn
0x1800402ad  mov     rax, [rbp+3E0h+var_460]
0x1800402b1  mov     rcx, [rax]
0x1800402b4  mov     rbx, [rcx+138h]
0x1800402bb  lea     rcx, [rbp+3E0h+bstrString]
0x1800402bf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800402c4  mov     rcx, [rbp+3E0h+var_460]
0x1800402c8  mov     rdx, rax
0x1800402cb  mov     rax, rbx
0x1800402ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402d3  mov     r12d, 1
0x1800402d9  cmp     eax, r12d
0x1800402dc  jz      short loc_1800402E5
0x1800402de  mov     edx, eax
0x1800402e0  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800402e5  xor     ecx, ecx; bstrString
0x1800402e7  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800402ec  lea     rcx, aDatacollectors_36; "/DataCollectorSet"
0x1800402f3  call    cs:__imp_SysAllocString
0x1800402f9  mov     rbx, rax
0x1800402fc  test    rax, rax
0x1800402ff  jz      loc_18004076E
0x180040305  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004030c  lea     r15, qword_180147320
0x180040313  jz      loc_1800403E3
0x180040319  mov     rdx, 4000000000000200h
0x180040323  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004032a  jz      loc_1800403E3
0x180040330  mov     rax, cs:qword_180169748
0x180040337  and     rax, rdx
0x18004033a  cmp     cs:qword_180169748, rax
0x180040341  jnz     loc_1800403E3
0x180040347  mov     rcx, rbx; bstr
0x18004034a  call    cs:__imp_SysStringByteLen
0x180040350  cmp     dword ptr cs:xmmword_180169738, r14d
0x180040357  mov     eax, eax
0x180040359  mov     [rbp+3E0h+var_450], rax
0x18004035d  mov     [rsp+4E0h+var_468], rbx
0x180040362  mov     dword ptr [rsp+4E0h+var_470], r14d
0x180040367  jz      short loc_1800403E3
0x180040369  mov     rdx, 4000000000000200h
0x180040373  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004037a  jz      short loc_1800403E3
0x18004037c  mov     rax, cs:qword_180169748
0x180040383  and     rax, rdx
0x180040386  cmp     cs:qword_180169748, rax
0x18004038d  jnz     short loc_1800403E3
0x18004038f  mov     ecx, 8
0x180040394  lea     rax, [rbp+3E0h+var_450]
0x180040398  mov     [rsp+4E0h+var_490], rcx
0x18004039d  lea     rdx, PLA_EVENT_ALLOC_STRING
0x1800403a4  mov     [rsp+4E0h+var_498], rax
0x1800403a9  mov     r9, r15
0x1800403ac  mov     [rsp+4E0h+var_4A0], rcx
0x1800403b1  lea     rax, [rsp+4E0h+var_468]
0x1800403b6  mov     [rsp+4E0h+var_4A8], rax
0x1800403bb  lea     r8d, [rcx-4]
0x1800403bf  lea     rax, [rsp+4E0h+var_470]
0x1800403c4  mov     [rsp+4E0h+var_4B0], 4
0x1800403cd  mov     [rsp+4E0h+var_4B8], rax
0x1800403d2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800403d9  mov     [rsp+4E0h+var_4C0], r12
0x1800403de  call    EventingWriteEvent
0x1800403e3  mov     rcx, [rbp+3E0h+var_460]
0x1800403e7  lea     r8, [rbp+3E0h+var_458]
0x1800403eb  mov     rdx, rbx
0x1800403ee  mov     r14, rbx
0x1800403f1  mov     rax, [rcx]
0x1800403f4  mov     rax, [rax+128h]
0x1800403fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040400  mov     ebx, eax
0x180040402  test    eax, eax
0x180040404  jns     loc_1800404BA
0x18004040a  xor     esi, esi
0x18004040c  mov     dword ptr [rsp+4E0h+var_468], eax
0x180040410  cmp     dword ptr cs:xmmword_180169738, esi
0x180040416  mov     dword ptr [rsp+4E0h+var_470], esi
0x18004041a  jz      loc_180040214
0x180040420  mov     rdx, 4000000000000800h; unsigned __int64
0x18004042a  test    qword ptr cs:xmmword_180169738+8, rdx
0x180040431  jz      loc_180040214
0x180040437  mov     rax, cs:qword_180169748
0x18004043e  and     rax, rdx
0x180040441  cmp     cs:qword_180169748, rax
0x180040448  jnz     loc_180040214
0x18004044e  lea     rcx, [rbp+3E0h+var_3C0]; unsigned __int16 *
0x180040452  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180040457  lea     rcx, [rbp+3E0h+var_3C0]
0x18004045b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004045f  inc     rax
0x180040462  cmp     [rcx+rax*2], si
0x180040466  jnz     short loc_18004045F
0x180040468  lea     ecx, [rax+rax]
0x18004046b  lea     rax, [rbp+3E0h+var_3C0]
0x18004046f  add     rcx, 2
0x180040473  mov     [rsp+4E0h+var_480], rcx
0x180040478  mov     ecx, 4
0x18004047d  mov     [rsp+4E0h+var_488], rax
0x180040482  lea     rax, aDatacollectors_62; "DataCollectorSet::SetXml"
0x180040489  mov     [rsp+4E0h+var_490], 19h
0x180040492  mov     [rsp+4E0h+var_498], rax
0x180040497  lea     rax, [rsp+4E0h+var_470]
0x18004049c  mov     [rsp+4E0h+var_4A0], rcx
0x1800404a1  mov     [rsp+4E0h+var_4A8], rax
0x1800404a6  mov     [rsp+4E0h+var_4B0], r12
0x1800404ab  mov     [rsp+4E0h+var_4B8], r15
0x1800404b0  mov     [rsp+4E0h+var_4C0], rcx
0x1800404b5  jmp     loc_180040830
0x1800404ba  cmp     eax, r12d
0x1800404bd  jnz     short loc_180040537
0x1800404bf  xor     esi, esi
0x1800404c1  mov     ebx, 80070057h
0x1800404c6  cmp     dword ptr cs:xmmword_180169738, esi
0x1800404cc  mov     dword ptr [rsp+4E0h+var_470], esi
0x1800404d0  mov     dword ptr [rsp+4E0h+var_468], ebx
0x1800404d4  jz      loc_180040214
0x1800404da  mov     rdx, 4000000000000800h; unsigned __int64
0x1800404e4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800404eb  jz      loc_180040214
0x1800404f1  mov     rax, cs:qword_180169748
0x1800404f8  and     rax, rdx
0x1800404fb  cmp     cs:qword_180169748, rax
0x180040502  jnz     loc_180040214
0x180040508  lea     rcx, [rbp+3E0h+var_340]; unsigned __int16 *
0x18004050f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180040514  lea     rcx, [rbp+3E0h+var_340]
0x18004051b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004051f  inc     rax
0x180040522  cmp     [rcx+rax*2], si
0x180040526  jnz     short loc_18004051F
0x180040528  lea     ecx, [rax+rax]
0x18004052b  lea     rax, [rbp+3E0h+var_340]
0x180040532  jmp     loc_18004046F
0x180040537  mov     rax, [rdi]
0x18004053a  mov     rcx, rdi
0x18004053d  mov     rax, [rax+258h]
0x180040544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040549  mov     ebx, eax
0x18004054b  test    eax, eax
0x18004054d  jns     short loc_1800405C2
0x18004054f  xor     esi, esi
0x180040551  mov     dword ptr [rsp+4E0h+var_468], eax
0x180040555  cmp     dword ptr cs:xmmword_180169738, esi
0x18004055b  mov     dword ptr [rsp+4E0h+var_470], esi
0x18004055f  jz      loc_180040214
0x180040565  mov     rdx, 4000000000000800h; unsigned __int64
0x18004056f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180040576  jz      loc_180040214
0x18004057c  mov     rax, cs:qword_180169748
0x180040583  and     rax, rdx
0x180040586  cmp     cs:qword_180169748, rax
0x18004058d  jnz     loc_180040214
0x180040593  lea     rcx, [rbp+3E0h+var_2C0]; unsigned __int16 *
0x18004059a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004059f  lea     rcx, [rbp+3E0h+var_2C0]
0x1800405a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800405aa  inc     rax
0x1800405ad  cmp     [rcx+rax*2], si
  ... truncated ...
```
