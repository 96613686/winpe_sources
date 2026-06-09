# NDXGI::CUMDAdapter::OpenAdapter10(unsigned __int64)

- ea: `0x1800ba720`
- end: `0x1800ba836`
- name: `?OpenAdapter10@CUMDAdapter@NDXGI@@QEAAJ_K@Z`
- size: `278`
- prototype: `__int64 __fastcall(NDXGI::CUMDAdapter *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800aee3c`

## callees

- `0x1800229a0`
- `0x180048f24`
- `0x18007eee0`
- `0x1800ba720`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba789`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ba76f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ba76f`

## string_xrefs

- `0x1800ba768`: `OpenAdapter10`
- `0x1800ba809`: `OpenAdapter10`
- `0x1800ba7a7`: `Failed to retrieve OpenAdapter10`

## pseudocode

```c
__int64 __fastcall NDXGI::CUMDAdapter::OpenAdapter10(NDXGI::CUMDAdapter *this, __int64 a2)
{
  HMODULE v4; // rcx
  FARPROC ProcAddress; // rbp
  signed int LastError; // eax
  __int64 v7; // r9
  signed int v8; // ebx
  int v9; // eax
  __int64 v10; // r9
  NDXGI::CUMDAdapter *v12; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+38h] [rbp-50h]
  int v14; // [rsp+40h] [rbp-48h]
  int v15; // [rsp+44h] [rbp-44h]
  char *v16; // [rsp+48h] [rbp-40h]
  char *v17; // [rsp+50h] [rbp-38h]
  char v18; // [rsp+90h] [rbp+8h] BYREF

  v17 = 0;
  v12 = this;
  v13 = 0;
  v14 = HIDWORD(a2);
  v15 = a2;
  v16 = (char *)this + 40;
  v4 = *(HMODULE *)this;
  if ( !v4 )
    v4 = (HMODULE)*((_QWORD *)this + 10);
  ProcAddress = GetProcAddress(v4, "OpenAdapter10");
  v17 = (char *)this + 864;
  if ( ProcAddress )
    goto LABEL_8;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_8:
    CETWEventPair::CETWEventPair((CETWEventPair *)&v18, &EventInitiatingUMDOpenAdapter, &EventFinishedUMDOpenAdapter, 1);
    v9 = ((__int64 (__fastcall *)(NDXGI::CUMDAdapter **))ProcAddress)(&v12);
    v8 = v9;
    if ( v9 < 0 )
    {
      CModule::RecordJournal((CModule *)&g_Module, v9, "OpenAdapter10", v10, 1);
    }
    else
    {
      *((_QWORD *)this + 113) = v13;
      *((_QWORD *)this + 114) = a2;
    }
    CETWEventPair::~CETWEventPair((CETWEventPair *)&v18);
  }
  else
  {
    CModule::RecordJournal((CModule *)&g_Module, v8, "Failed to retrieve OpenAdapter10", v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ba720  mov     r11, rsp
0x1800ba723  push    rbx
0x1800ba724  push    rbp
0x1800ba725  push    rsi
0x1800ba726  push    rdi
0x1800ba727  sub     rsp, 68h
0x1800ba72b  mov     rsi, rdx
0x1800ba72e  mov     rdi, rcx
0x1800ba731  mov     qword ptr [r11-38h], 0
0x1800ba739  mov     [r11-58h], rcx
0x1800ba73d  mov     qword ptr [r11-50h], 0
0x1800ba745  mov     rax, rdx
0x1800ba748  shr     rax, 20h
0x1800ba74c  mov     [rsp+88h+var_48], eax
0x1800ba750  mov     [rsp+88h+var_44], esi
0x1800ba754  lea     rax, [rcx+28h]
0x1800ba758  mov     [r11-40h], rax
0x1800ba75c  mov     rcx, [rcx]
0x1800ba75f  test    rcx, rcx
0x1800ba762  jnz     short loc_1800BA768
0x1800ba764  mov     rcx, [rdi+50h]; hModule
0x1800ba768  lea     rdx, aOpenadapter10_0; "OpenAdapter10"
0x1800ba76f  call    cs:__imp_GetProcAddress
0x1800ba775  mov     rbp, rax
0x1800ba778  lea     rcx, [rdi+360h]
0x1800ba77f  mov     [rsp+88h+var_38], rcx
0x1800ba784  test    rax, rax
0x1800ba787  jnz     short loc_1800BA7BE
0x1800ba789  call    cs:__imp_GetLastError
0x1800ba78f  mov     ebx, eax
0x1800ba791  test    eax, eax
0x1800ba793  jle     short loc_1800BA79E
0x1800ba795  movzx   ebx, ax
0x1800ba798  or      ebx, 80070000h
0x1800ba79e  test    ebx, ebx
0x1800ba7a0  jns     short loc_1800BA7BE
0x1800ba7a2  mov     [rsp+88h+var_68], 1; bool
0x1800ba7a7  lea     r8, aFailedToRetrie; "Failed to retrieve OpenAdapter10"
0x1800ba7ae  mov     edx, ebx; unsigned int
0x1800ba7b0  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800ba7b7  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800ba7bc  jmp     short loc_1800BA82B
0x1800ba7be  mov     r9b, 1; bool
0x1800ba7c1  lea     r8, EventFinishedUMDOpenAdapter; struct _EVENT_DESCRIPTOR *
0x1800ba7c8  lea     rdx, EventInitiatingUMDOpenAdapter; struct _EVENT_DESCRIPTOR *
0x1800ba7cf  lea     rcx, [rsp+88h+arg_0]; this
0x1800ba7d7  call    ??0CETWEventPair@@QEAA@PEBU_EVENT_DESCRIPTOR@@0_N@Z; CETWEventPair::CETWEventPair(_EVENT_DESCRIPTOR const *,_EVENT_DESCRIPTOR const *,bool)
0x1800ba7dc  lea     rcx, [rsp+88h+var_58]
0x1800ba7e1  mov     rax, rbp
0x1800ba7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba7e9  mov     ebx, eax
0x1800ba7eb  test    eax, eax
0x1800ba7ed  js      short loc_1800BA804
0x1800ba7ef  mov     rcx, [rsp+88h+var_50]
0x1800ba7f4  mov     [rdi+388h], rcx
0x1800ba7fb  mov     [rdi+390h], rsi
0x1800ba802  jmp     short loc_1800BA81E
0x1800ba804  mov     [rsp+88h+var_68], 1; bool
0x1800ba809  lea     r8, aOpenadapter10_0; "OpenAdapter10"
0x1800ba810  mov     edx, eax; unsigned int
0x1800ba812  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800ba819  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800ba81e  lea     rcx, [rsp+88h+arg_0]; this
0x1800ba826  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x1800ba82b  mov     eax, ebx
0x1800ba82d  add     rsp, 68h
0x1800ba831  pop     rdi
0x1800ba832  pop     rsi
0x1800ba833  pop     rbp
0x1800ba834  pop     rbx
0x1800ba835  retn
```
