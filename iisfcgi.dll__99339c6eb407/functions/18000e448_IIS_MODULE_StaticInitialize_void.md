# IIS_MODULE::StaticInitialize(void)

- ea: `0x18000e448`
- end: `0x18000e506`
- name: `?StaticInitialize@IIS_MODULE@@SAJXZ`
- size: `190`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000b088`

## callees

- `0x180001008`
- `0x18000e448`
- `0x18000edde`
- `0x18000ee10`

## import_xrefs

- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18000e4c3`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x18000e4c3`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x18000e4a7`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x18000e4a7`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000e462`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000e462`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000e4eb`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000e4eb`

## string_xrefs

- `0x18000e4a0`: `System\CurrentControlSet\Services\w3svc\Parameters`

## pseudocode

```c
__int64 IIS_MODULE::StaticInitialize(void)
{
  void *v0; // rax
  unsigned int v1; // ebx
  __int64 i; // rbx
  _BYTE v4[56]; // [rsp+20h] [rbp-48h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v4);
  v0 = operator new(0xACu);
  IIS_MODULE::sm_pfSendUtf8 = v0;
  if ( v0 )
  {
    memset_0(v0, 0, 0xACu);
    if ( (int)ReadMultiStringParameterValueFromAnyService(
                L"System\\CurrentControlSet\\Services\\w3svc\\Parameters",
                L"FastCGIUtf8ServerVariables",
                (struct MULTISZ *)v4) >= 0 )
    {
      for ( i = 0; i != 43; ++i )
      {
        if ( MULTISZ::FindStringNoCase((MULTISZ *)v4, (const unsigned __int16 *)(&IIS_MODULE::sm_UnicodeSVars)[i]) )
          *((_DWORD *)IIS_MODULE::sm_pfSendUtf8 + i) = 1;
      }
    }
    v1 = 0;
  }
  else
  {
    v1 = -2147024888;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v4);
  return v1;
}

```

## disassembly

```asm
0x18000e448  push    rbx
0x18000e44a  sub     rsp, 60h
0x18000e44e  mov     rax, cs:__security_cookie
0x18000e455  xor     rax, rsp
0x18000e458  mov     [rsp+68h+var_10], rax
0x18000e45d  lea     rcx, [rsp+68h+var_48]
0x18000e462  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000e468  mov     ebx, 0ACh
0x18000e46d  mov     ecx, ebx; Size
0x18000e46f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e474  mov     cs:?sm_pfSendUtf8@IIS_MODULE@@0PEAHEA, rax; int * IIS_MODULE::sm_pfSendUtf8
0x18000e47b  test    rax, rax
0x18000e47e  jnz     short loc_18000E487
0x18000e480  mov     ebx, 80070008h
0x18000e485  jmp     short loc_18000E4E6
0x18000e487  mov     r8, rbx; Size
0x18000e48a  xor     edx, edx; Val
0x18000e48c  mov     rcx, rax; void *
0x18000e48f  call    memset_0
0x18000e494  lea     r8, [rsp+68h+var_48]
0x18000e499  lea     rdx, aFastcgiutf8ser; "FastCGIUtf8ServerVariables"
0x18000e4a0  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\w3"...
0x18000e4a7  call    cs:__imp_?ReadMultiStringParameterValueFromAnyService@@YAJPEBG0PEAVMULTISZ@@@Z; ReadMultiStringParameterValueFromAnyService(ushort const *,ushort const *,MULTISZ *)
0x18000e4ad  test    eax, eax
0x18000e4af  js      short loc_18000E4E4
0x18000e4b1  xor     ebx, ebx
0x18000e4b3  lea     rdx, ?sm_UnicodeSVars@IIS_MODULE@@0PAPEBGA; ushort const * near * IIS_MODULE::sm_UnicodeSVars
0x18000e4ba  mov     rdx, [rdx+rbx*8]
0x18000e4be  lea     rcx, [rsp+68h+var_48]
0x18000e4c3  call    cs:__imp_?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindStringNoCase(ushort const *)
0x18000e4c9  test    eax, eax
0x18000e4cb  jz      short loc_18000E4DB
0x18000e4cd  mov     rax, cs:?sm_pfSendUtf8@IIS_MODULE@@0PEAHEA; int * IIS_MODULE::sm_pfSendUtf8
0x18000e4d4  mov     dword ptr [rax+rbx*4], 1
0x18000e4db  inc     rbx
0x18000e4de  cmp     rbx, 2Bh ; '+'
0x18000e4e2  jnz     short loc_18000E4B3
0x18000e4e4  xor     ebx, ebx
0x18000e4e6  lea     rcx, [rsp+68h+var_48]
0x18000e4eb  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000e4f1  mov     eax, ebx
0x18000e4f3  mov     rcx, [rsp+68h+var_10]
0x18000e4f8  xor     rcx, rsp; StackCookie
0x18000e4fb  call    __security_check_cookie
0x18000e500  add     rsp, 60h
0x18000e504  pop     rbx
0x18000e505  retn
```
