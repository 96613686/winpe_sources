# FillErrorInfo(ushort const *,ulong)

- ea: `0x1800f02f4`
- end: `0x1800f0415`
- name: `?FillErrorInfo@@YAJPEBGK@Z`
- size: `289`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f0418`

## callees

- `0x1800f02f4`
- `0x180106100`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x1800f03d7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800f03d7`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800f0320`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800f0320`

## string_xrefs

- `0x1800f0370`: `complib.hlp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HRESULT __fastcall FillErrorInfo(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v2; // edi
  const unsigned __int16 *v3; // rbx
  int v4; // ebx
  HRESULT result; // eax
  BOOL v6; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  HRESULT v9; // [rsp+20h] [rbp-58h]
  _QWORD v10[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h]
  _QWORD v12[6]; // [rsp+48h] [rbp-30h] BYREF
  ICreateErrorInfo *v17; // [rsp+90h] [rbp+18h] BYREF
  IErrorInfo *perrinfo; // [rsp+98h] [rbp+20h] BYREF

  v2 = a2;
  v3 = a1;
  perrinfo = 0;
  v11 = 0;
  try
  {
    try
    {
      result = CreateErrorInfo(&v17);
    }
    catch ( Exception *v10 )
    {
      v11 = v10[0];
      throw;
    }
  }
  catch ( ... )
  {
    v12[1] = 0;
    v12[0] = &DelegatingException::`vftable';
    v12[2] = -1;
    v10[1] = v11;
    v6 = v11 != 0;
    LODWORD(v11) = v6;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD *))(v12[0] + 16LL))(v12);
    if ( v6 )
      LODWORD(v11) = 0;
    DelegatingException::~DelegatingException((DelegatingException *)v12);
    v2 = a2;
    v3 = a1;
    result = v9;
  }
  if ( result >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v17->lpVtbl->SetDescription)(v17, v3);
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))v17->lpVtbl->SetHelpFile)(v17, L"complib.hlp");
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))v17->lpVtbl->SetHelpContext)(v17, v2);
        if ( v4 >= 0 )
        {
          v4 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v17->lpVtbl->QueryInterface)(
                 v17,
                 &IID_IErrorInfo,
                 &perrinfo);
          if ( v4 >= 0 )
            SetErrorInfo(0, perrinfo);
        }
      }
    }
    ((void (__fastcall *)(ICreateErrorInfo *))v17->lpVtbl->Release)(v17);
    if ( perrinfo )
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800f02f4  mov     [rsp+arg_8], edx
0x1800f02f8  mov     r11, rsp
0x1800f02fb  mov     [r11+8], rcx
0x1800f02ff  push    rbx
0x1800f0300  push    rdi
0x1800f0301  sub     rsp, 68h
0x1800f0305  mov     edi, edx
0x1800f0307  mov     rbx, rcx
0x1800f030a  and     qword ptr [r11+20h], 0
0x1800f030f  and     qword ptr [r11-38h], 0
0x1800f0314  lea     rax, [r11-40h]
0x1800f0318  mov     [r11-50h], rax
0x1800f031c  lea     rcx, [r11+18h]; pperrinfo
0x1800f0320  call    cs:__imp_CreateErrorInfo
0x1800f0326  mov     [rsp+78h+var_58], eax
0x1800f032a  jmp     short loc_1800F033F
0x1800f032c  mov     edi, [rsp+78h+arg_8]
0x1800f0333  mov     rbx, [rsp+78h+arg_0]
0x1800f033b  mov     eax, [rsp+78h+var_58]
0x1800f033f  test    eax, eax
0x1800f0341  js      loc_1800F040E
0x1800f0347  mov     rcx, [rsp+78h+arg_10]
0x1800f034f  mov     rax, [rcx]
0x1800f0352  mov     rdx, rbx
0x1800f0355  mov     rax, [rax+28h]
0x1800f0359  call    cs:__guard_dispatch_icall_fptr
0x1800f035f  mov     ebx, eax
0x1800f0361  test    eax, eax
0x1800f0363  js      short loc_1800F03DD
0x1800f0365  mov     rcx, [rsp+78h+arg_10]
0x1800f036d  mov     rax, [rcx]
0x1800f0370  lea     rdx, aComplibHlp; "complib.hlp"
0x1800f0377  mov     rax, [rax+30h]
0x1800f037b  call    cs:__guard_dispatch_icall_fptr
0x1800f0381  mov     ebx, eax
0x1800f0383  test    eax, eax
0x1800f0385  js      short loc_1800F03DD
0x1800f0387  mov     rcx, [rsp+78h+arg_10]
0x1800f038f  mov     rax, [rcx]
0x1800f0392  mov     edx, edi
0x1800f0394  mov     rax, [rax+38h]
0x1800f0398  call    cs:__guard_dispatch_icall_fptr
0x1800f039e  mov     ebx, eax
0x1800f03a0  test    eax, eax
0x1800f03a2  js      short loc_1800F03DD
0x1800f03a4  mov     rcx, [rsp+78h+arg_10]
0x1800f03ac  mov     rax, [rcx]
0x1800f03af  lea     r8, [rsp+78h+perrinfo]
0x1800f03b7  lea     rdx, IID_IErrorInfo
0x1800f03be  mov     rax, [rax]
0x1800f03c1  call    cs:__guard_dispatch_icall_fptr
0x1800f03c7  mov     ebx, eax
0x1800f03c9  test    eax, eax
0x1800f03cb  js      short loc_1800F03DD
0x1800f03cd  mov     rdx, [rsp+78h+perrinfo]; perrinfo
0x1800f03d5  xor     ecx, ecx; dwReserved
0x1800f03d7  call    cs:__imp_SetErrorInfo
0x1800f03dd  mov     rcx, [rsp+78h+arg_10]
0x1800f03e5  mov     rax, [rcx]
0x1800f03e8  mov     rax, [rax+10h]
0x1800f03ec  call    cs:__guard_dispatch_icall_fptr
0x1800f03f2  mov     rcx, [rsp+78h+perrinfo]
0x1800f03fa  test    rcx, rcx
0x1800f03fd  jz      short loc_1800F040C
0x1800f03ff  mov     rax, [rcx]
0x1800f0402  mov     rax, [rax+10h]
0x1800f0406  call    cs:__guard_dispatch_icall_fptr
0x1800f040c  mov     eax, ebx
0x1800f040e  add     rsp, 68h
0x1800f0412  pop     rdi
0x1800f0413  pop     rbx
0x1800f0414  retn
```
