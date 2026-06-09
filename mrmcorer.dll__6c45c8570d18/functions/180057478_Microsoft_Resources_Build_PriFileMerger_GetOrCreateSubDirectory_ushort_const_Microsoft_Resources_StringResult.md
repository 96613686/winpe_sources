# Microsoft::Resources::Build::PriFileMerger::GetOrCreateSubDirectory(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x180057478`
- end: `0x1800575a1`
- name: `?GetOrCreateSubDirectory@PriFileMerger@Build@Resources@Microsoft@@SAJPEBGPEAVStringResult@34@@Z`
- size: `297`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056f28`
- `0x1800911f0`

## callees

- `0x180017960`
- `0x180028510`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x18003c030`
- `0x180057478`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005752b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005752b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057538`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180057521`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180057521`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Build::PriFileMerger::GetOrCreateSubDirectory(
        const unsigned __int16 *a1,
        struct Microsoft::Resources::StringResult *a2)
{
  Microsoft::Resources::StringResult *v4; // rdx
  const unsigned __int16 *Ref; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  const WCHAR *v9; // rdx
  int v10; // eax
  const WCHAR *v11; // rcx
  signed int LastError; // eax
  int v14[2]; // [rsp+20h] [rbp-28h] BYREF
  int v15[8]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  DefStringResult_InitBuf(v15);
  *(_QWORD *)v14 = v15;
  Ref = Microsoft::Resources::StringResult::GetRef(v4);
  v6 = DefStringResult_SetCopy(v15, Ref);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 244;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmex\\primerge.cpp",
      (const char *)(unsigned int)v6,
      v14[0]);
    goto LABEL_23;
  }
  v6 = DefStringResult_ConcatPathElement(*(_QWORD *)v14, a1, 92);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 245;
    goto LABEL_5;
  }
  if ( *(_QWORD *)v14
    && (**(_QWORD **)v14 || !*(_DWORD *)(*(_QWORD *)v14 + 8LL))
    && (*(_DWORD *)(*(_QWORD *)v14 + 8LL) || !**(_QWORD **)v14) )
  {
    v9 = *(const WCHAR **)(*(_QWORD *)v14 + 16LL);
    v10 = 0;
  }
  else
  {
    v9 = 0;
    v10 = -2147024809;
  }
  v11 = 0;
  if ( v10 >= 0 )
    v11 = v9;
  if ( CreateDirectoryW(v11, 0) || GetLastError() == 183 )
  {
    v6 = DefStringResult_ConcatPathElement(*(_QWORD *)a2, a1, 92);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_23;
    }
    v8 = 251;
    goto LABEL_5;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v7 = LastError;
LABEL_23:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v14);
  return v7;
}

```

## disassembly

```asm
0x180057478  mov     [rsp+arg_0], rbx
0x18005747d  mov     [rsp+arg_8], rsi
0x180057482  push    rdi
0x180057483  sub     rsp, 40h
0x180057487  mov     rdi, rcx
0x18005748a  mov     rsi, rdx
0x18005748d  lea     rcx, [rsp+48h+var_20]
0x180057492  call    DefStringResult_InitBuf
0x180057497  lea     rcx, [rsp+48h+var_20]
0x18005749c  mov     qword ptr [rsp+48h+var_28], rcx; int
0x1800574a1  mov     rcx, rdx; this
0x1800574a4  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x1800574a9  mov     rdx, rax
0x1800574ac  lea     rcx, [rsp+48h+var_20]
0x1800574b1  call    DefStringResult_SetCopy
0x1800574b6  mov     ebx, eax
0x1800574b8  test    eax, eax
0x1800574ba  jns     short loc_1800574C3
0x1800574bc  mov     edx, 0F4h
0x1800574c1  jmp     short loc_1800574E1
0x1800574c3  mov     rcx, qword ptr [rsp+48h+var_28]
0x1800574c8  mov     r8d, 5Ch ; '\'
0x1800574ce  mov     rdx, rdi
0x1800574d1  call    DefStringResult_ConcatPathElement
0x1800574d6  mov     ebx, eax
0x1800574d8  test    eax, eax
0x1800574da  jns     short loc_1800574FA
0x1800574dc  mov     edx, 0F5h; void *
0x1800574e1  mov     rcx, [rsp+48h]; this
0x1800574e6  lea     r8, aMinkernelMrtMr_2; "minkernel\\mrt\\mrm\\mrmex\\primerge.cp"...
0x1800574ed  mov     r9d, eax; char *
0x1800574f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800574f5  jmp     loc_180057585
0x1800574fa  mov     rax, qword ptr [rsp+48h+var_28]
0x1800574ff  test    rax, rax
0x180057502  jz      short loc_180057510
0x180057504  cmp     qword ptr [rax], 0
0x180057508  jnz     short loc_18005754E
0x18005750a  cmp     dword ptr [rax+8], 0
0x18005750e  jbe     short loc_18005754E
0x180057510  xor     edx, edx
0x180057512  mov     eax, 80070057h
0x180057517  xor     ecx, ecx
0x180057519  test    eax, eax
0x18005751b  cmovns  rcx, rdx; lpPathName
0x18005751f  xor     edx, edx; lpSecurityAttributes
0x180057521  call    cs:__imp_CreateDirectoryW
0x180057527  test    eax, eax
0x180057529  jnz     short loc_180057562
0x18005752b  call    cs:__imp_GetLastError
0x180057531  cmp     eax, 0B7h
0x180057536  jz      short loc_180057562
0x180057538  call    cs:__imp_GetLastError
0x18005753e  test    eax, eax
0x180057540  jle     short loc_18005754A
0x180057542  movzx   eax, ax
0x180057545  or      eax, 80070000h
0x18005754a  mov     ebx, eax
0x18005754c  jmp     short loc_180057585
0x18005754e  cmp     dword ptr [rax+8], 0
0x180057552  jnz     short loc_18005755A
0x180057554  cmp     qword ptr [rax], 0
0x180057558  jnz     short loc_180057510
0x18005755a  mov     rdx, [rax+10h]
0x18005755e  xor     eax, eax
0x180057560  jmp     short loc_180057517
0x180057562  mov     rcx, [rsi]
0x180057565  mov     r8d, 5Ch ; '\'
0x18005756b  mov     rdx, rdi
0x18005756e  call    DefStringResult_ConcatPathElement
0x180057573  mov     ebx, eax
0x180057575  test    eax, eax
0x180057577  jns     short loc_180057583
0x180057579  mov     edx, 0FBh
0x18005757e  jmp     loc_1800574E1
0x180057583  xor     ebx, ebx
0x180057585  lea     rcx, [rsp+48h+var_28]; this
0x18005758a  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18005758f  mov     rsi, [rsp+48h+arg_8]
0x180057594  mov     eax, ebx
0x180057596  mov     rbx, [rsp+48h+arg_0]
0x18005759b  add     rsp, 40h
0x18005759f  pop     rdi
0x1800575a0  retn
```
