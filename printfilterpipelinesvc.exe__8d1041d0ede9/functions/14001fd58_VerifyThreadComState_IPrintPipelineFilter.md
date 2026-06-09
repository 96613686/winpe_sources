# VerifyThreadComState(IPrintPipelineFilter *)

- ea: `0x14001fd58`
- end: `0x14001fe9f`
- name: `?VerifyThreadComState@@YAXPEAUIPrintPipelineFilter@@@Z`
- size: `327`
- prototype: `void __fastcall(struct IPrintPipelineFilter *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001d428`

## callees

- `0x140002070`
- `0x1400075d4`
- `0x14000fa68`
- `0x140016660`
- `0x14001fd58`
- `0x140063010`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x14001fe2b`
- `KERNEL32!OutputDebugStringA` at `0x14001fe58`
- `KERNEL32!OutputDebugStringA` at `0x14001fe2b`
- `KERNEL32!OutputDebugStringA` at `0x14001fe58`
- `KERNEL32!IsDebuggerPresent` at `0x14001fe11`
- `KERNEL32!IsDebuggerPresent` at `0x14001fe11`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x14001fd91`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x14001fd91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fe5e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001fe5e`

## string_xrefs

- `0x14001fe24`: `PrintFilterPipelineSvc: A print filter did not uninitialize COM properly on the current thread!\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VerifyThreadComState(struct IPrintPipelineFilter *a1)
{
  char v2; // bl
  int v3; // [rsp+30h] [rbp-F8h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-F0h] BYREF
  CHAR OutputString[208]; // [rsp+40h] [rbp-E8h] BYREF

  v2 = 1;
  while ( 1 )
  {
    ppv = 0;
    if ( CoGetObjectContext(&IID_IComThreadingInfo, &ppv) < 0 )
      break;
    v3 = -1;
    if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 24LL))(ppv, &v3) < 0 || v3 == 1 )
      break;
    if ( v2 )
    {
      v2 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids, a1);
      }
      if ( IsDebuggerPresent() || MEMORY[0x7FFE02D4] )
      {
        OutputDebugStringA("PrintFilterPipelineSvc: A print filter did not uninitialize COM properly on the current thread!\n");
        if ( (int)StringCchPrintfA(
                    OutputString,
                    0xC8u,
                    "The IPrintPipelineFilter for the filter is %p. Use \"ln poi(%p)\" to find the filter\n",
                    a1,
                    a1) >= 0 )
          OutputDebugStringA(OutputString);
      }
    }
    CoUninitialize();
    PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppv);
  }
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)&ppv);
}

```

## disassembly

```asm
0x14001fd58  mov     [rsp+arg_8], rbx
0x14001fd5d  push    rdi
0x14001fd5e  sub     rsp, 120h
0x14001fd65  mov     rax, cs:__security_cookie
0x14001fd6c  xor     rax, rsp
0x14001fd6f  mov     [rsp+128h+var_18], rax
0x14001fd77  mov     rdi, rcx
0x14001fd7a  mov     bl, 1
0x14001fd7c  mov     [rsp+128h+ppv], 0
0x14001fd85  lea     rdx, [rsp+128h+ppv]; ppv
0x14001fd8a  lea     rcx, IID_IComThreadingInfo; riid
0x14001fd91  call    cs:__imp_CoGetObjectContext
0x14001fd97  test    eax, eax
0x14001fd99  js      loc_14001FE74
0x14001fd9f  mov     [rsp+128h+var_F8], 0FFFFFFFFh
0x14001fda7  mov     rcx, [rsp+128h+ppv]
0x14001fdac  mov     rax, [rcx]
0x14001fdaf  lea     rdx, [rsp+128h+var_F8]
0x14001fdb4  mov     rax, [rax+18h]
0x14001fdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fdbd  test    eax, eax
0x14001fdbf  js      loc_14001FE74
0x14001fdc5  cmp     [rsp+128h+var_F8], 1
0x14001fdca  jz      loc_14001FE74
0x14001fdd0  test    bl, bl
0x14001fdd2  jz      loc_14001FE5E
0x14001fdd8  xor     bl, bl
0x14001fdda  lea     rax, WPP_GLOBAL_Control
0x14001fde1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fde8  cmp     rcx, rax
0x14001fdeb  jz      short loc_14001FE11
0x14001fded  test    byte ptr [rcx+1Ch], 8
0x14001fdf1  jz      short loc_14001FE11
0x14001fdf3  cmp     byte ptr [rcx+19h], 1
0x14001fdf7  jb      short loc_14001FE11
0x14001fdf9  mov     edx, 15h
0x14001fdfe  mov     r9, rdi
0x14001fe01  lea     r8, WPP_2af7783bcf603f06de9ad5fd8d382a30_Traceguids
0x14001fe08  mov     rcx, [rcx+10h]
0x14001fe0c  call    WPP_SF_q
0x14001fe11  call    cs:__imp_IsDebuggerPresent
0x14001fe17  test    eax, eax
0x14001fe19  jnz     short loc_14001FE24
0x14001fe1b  cmp     ds:7FFE02D4h, bl
0x14001fe22  jz      short loc_14001FE5E
0x14001fe24  lea     rcx, OutputString; "PrintFilterPipelineSvc: A print filter "...
0x14001fe2b  call    cs:__imp_OutputDebugStringA
0x14001fe31  mov     [rsp+128h+var_108], rdi
0x14001fe36  mov     r9, rdi
0x14001fe39  lea     r8, aTheIprintpipel; "The IPrintPipelineFilter for the filter"...
0x14001fe40  mov     edx, 0C8h; unsigned __int64
0x14001fe45  lea     rcx, [rsp+128h+OutputString]; char *
0x14001fe4a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14001fe4f  test    eax, eax
0x14001fe51  js      short loc_14001FE5E
0x14001fe53  lea     rcx, [rsp+128h+OutputString]; lpOutputString
0x14001fe58  call    cs:__imp_OutputDebugStringA
0x14001fe5e  call    cs:__imp_CoUninitialize
0x14001fe64  nop
0x14001fe65  lea     rcx, [rsp+128h+ppv]
0x14001fe6a  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001fe6f  jmp     loc_14001FD7C
0x14001fe74  lea     rcx, [rsp+128h+ppv]
0x14001fe79  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14001fe7e  mov     rcx, [rsp+128h+var_18]
0x14001fe86  xor     rcx, rsp; StackCookie
0x14001fe89  call    __security_check_cookie
0x14001fe8e  mov     rbx, [rsp+128h+arg_8]
0x14001fe96  add     rsp, 120h
0x14001fe9d  pop     rdi
0x14001fe9e  retn
```
