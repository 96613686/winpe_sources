# CDefragAsyncWorker::DisableAutomaticSleep(_GUID)

- ea: `0x18002afc0`
- end: `0x18002b10d`
- name: `?DisableAutomaticSleep@CDefragAsyncWorker@@UEAAJU_GUID@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CDefragAsyncWorker *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180017e34`
- `0x18002afc0`
- `0x18002b114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b0e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b018`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18002b0c6`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18002b0c6`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18002b092`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18002b092`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDefragAsyncWorker::DisableAutomaticSleep(struct _RTL_CRITICAL_SECTION *this, struct _GUID *a2)
{
  unsigned __int16 *v4; // rdi
  char *v5; // rax
  __int16 v6; // ax
  HANDLE v7; // rcx
  unsigned int v8; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-39h] BYREF
  _REASON_CONTEXT Context; // [rsp+30h] [rbp-29h] BYREF
  int StringResource; // [rsp+50h] [rbp-9h] BYREF
  __int16 v13; // [rsp+54h] [rbp-5h]
  __int16 v14; // [rsp+56h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StringResource,
    "CDefragAsyncWorker::DisableAutomaticSleep",
    1794,
    1);
  v4 = (unsigned __int16 *)&qword_18006F470;
  v10[0] = &qword_18006F470;
  v10[1] = 0;
  memset(&Context, 0, sizeof(Context));
  EnterCriticalSection(this + 1);
  if ( !HIDWORD(this[2].DebugInfo) || HIDWORD(this[2].DebugInfo) == 3 )
  {
    StringResource = -1996488694;
    v6 = 1807;
    goto LABEL_11;
  }
  v5 = (char *)this[3].LockSemaphore - *(_QWORD *)&a2->Data1;
  if ( !v5 )
    v5 = (char *)(this[3].SpinCount - *(_QWORD *)a2->Data4);
  if ( !v5 )
  {
    StringResource = CBsString::LoadStringResource((CBsString *)v10, g_hInstance, 0x323u);
    v4 = (unsigned __int16 *)v10[0];
    v6 = 1814;
    if ( StringResource < 0 )
    {
LABEL_11:
      v14 = v6;
      goto LABEL_12;
    }
    v13 = 1814;
    Context.Version = 0;
    Context.Flags = 1;
    Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)v10[0];
    v7 = PowerCreateRequest(&Context);
    *(_QWORD *)&this[4].LockCount = v7;
    v6 = 1822;
    if ( v7 == (HANDLE)-1LL )
    {
      StringResource = -1996488666;
      goto LABEL_11;
    }
    StringResource = 0;
    v13 = 1822;
    PowerSetRequest(v7, PowerRequestSystemRequired);
  }
LABEL_12:
  LeaveCriticalSection(this + 1);
  v8 = StringResource;
  CBsString::_FreeData(v4);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringResource);
  return v8;
}

```

## disassembly

```asm
0x18002afc0  push    rbp
0x18002afc2  push    rbx
0x18002afc3  push    rsi
0x18002afc4  push    rdi
0x18002afc5  push    r14
0x18002afc7  lea     rbp, [rsp-37h]
0x18002afcc  sub     rsp, 90h
0x18002afd3  mov     rsi, rdx
0x18002afd6  mov     rbx, rcx
0x18002afd9  mov     r9d, 1; unsigned __int16
0x18002afdf  mov     r8d, 702h; unsigned __int16
0x18002afe5  lea     rdx, aCdefragasyncwo_19; "CDefragAsyncWorker::DisableAutomaticSle"...
0x18002afec  lea     rcx, [rbp+57h+var_60]; this
0x18002aff0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002aff5  nop
0x18002aff6  lea     rdi, qword_18006F470
0x18002affd  mov     [rbp+57h+var_90], rdi
0x18002b001  mov     [rbp+57h+var_88], 0
0x18002b009  xorps   xmm0, xmm0
0x18002b00c  movups  xmmword ptr [rbp+57h+Context.Version], xmm0
0x18002b010  movups  xmmword ptr [rbp+57h+Context.Reason+8], xmm0
0x18002b014  lea     rcx, [rbx+28h]; lpCriticalSection
0x18002b018  call    cs:__imp_EnterCriticalSection
0x18002b01e  cmp     dword ptr [rbx+54h], 0
0x18002b022  jz      loc_18002B0CE
0x18002b028  cmp     dword ptr [rbx+54h], 3
0x18002b02c  jz      loc_18002B0CE
0x18002b032  mov     rax, [rbx+90h]
0x18002b039  sub     rax, [rsi]
0x18002b03c  jnz     short loc_18002B049
0x18002b03e  mov     rax, [rbx+98h]
0x18002b045  sub     rax, [rsi+8]
0x18002b049  test    rax, rax
0x18002b04c  jnz     loc_18002B0DE
0x18002b052  mov     r8d, 323h; uID
0x18002b058  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002b05f  lea     rcx, [rbp+57h+var_90]; this
0x18002b063  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x18002b068  mov     [rbp+57h+var_60], eax
0x18002b06b  mov     rdi, [rbp+57h+var_90]
0x18002b06f  test    eax, eax
0x18002b071  mov     eax, 716h
0x18002b076  js      short loc_18002B0DA
0x18002b078  mov     [rbp+57h+var_5C], ax
0x18002b07c  mov     [rbp+57h+Context.Version], 0
0x18002b083  mov     [rbp+57h+Context.Flags], 1
0x18002b08a  mov     qword ptr [rbp+57h+Context.Reason], rdi
0x18002b08e  lea     rcx, [rbp+57h+Context]; Context
0x18002b092  call    cs:__imp_PowerCreateRequest
0x18002b098  mov     rcx, rax; PowerRequest
0x18002b09b  mov     [rbx+0A8h], rax
0x18002b0a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b0a6  mov     eax, 71Eh
0x18002b0ab  jnz     short loc_18002B0B6
0x18002b0ad  mov     [rbp+57h+var_60], 89000026h
0x18002b0b4  jmp     short loc_18002B0DA
0x18002b0b6  mov     [rbp+57h+var_60], 0
0x18002b0bd  mov     [rbp+57h+var_5C], ax
0x18002b0c1  mov     edx, 1; RequestType
0x18002b0c6  call    cs:__imp_PowerSetRequest
0x18002b0cc  jmp     short loc_18002B0DE
0x18002b0ce  mov     [rbp+57h+var_60], 8900000Ah
0x18002b0d5  mov     eax, 70Fh
0x18002b0da  mov     [rbp+57h+var_5A], ax
0x18002b0de  lea     rcx, [rbx+28h]; lpCriticalSection
0x18002b0e2  call    cs:__imp_LeaveCriticalSection
0x18002b0e8  mov     ebx, [rbp+57h+var_60]
0x18002b0eb  mov     rcx, rdi; unsigned __int16 *
0x18002b0ee  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x18002b0f3  nop
0x18002b0f4  lea     rcx, [rbp+57h+var_60]; this
0x18002b0f8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002b0fd  mov     eax, ebx
0x18002b0ff  add     rsp, 90h
0x18002b106  pop     r14
0x18002b108  pop     rdi
0x18002b109  pop     rsi
0x18002b10a  pop     rbx
0x18002b10b  pop     rbp
0x18002b10c  retn
```
