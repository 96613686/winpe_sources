# CDtcInstanceConfig::SetLogPathAndSize(ushort *,long,long,ulong *)

- ea: `0x18004b750`
- end: `0x18004bad2`
- name: `?SetLogPathAndSize@CDtcInstanceConfig@@UEAAJPEAGJJPEAK@Z`
- size: `898`
- prototype: `__int64 __usercall@<rax>(CDtcInstanceConfig *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, int@<r9d>, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18001664c`
- `0x18004b750`
- `0x18004be10`
- `0x180085010`

## string_xrefs

- `0x18004b785`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004b87d`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004b8dd`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004ba5b`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004baa4`: `com\complus\dtc\dtc\msdtcprx\src\dtcinstanceconfig.cpp`
- `0x18004b79a`: `CDtcInstanceConfig::SetLogPathAndSize`
- `0x18004b7e6`: `CDtcInstanceConfig::SetLogPathAndSize`
- `0x18004b86a`: `CDtcInstanceConfig::SetLogPathAndSize`
- `0x18004ba05`: `CDtcInstanceConfig::SetLogPathAndSize`
- `0x18004ba98`: `CDtcInstanceConfig::SetLogPathAndSize`
- `0x18004b80b`: `SetLogPathAndSize is not supported on a remote host`
- `0x18004b839`: `VerifyLogPathSettings failed`
- `0x18004b97b`: `Failed to write log size in the registry.`
- `0x18004b9aa`: `Failed to set log file path.`

## pseudocode

```c
__int64 __fastcall CDtcInstanceConfig::SetLogPathAndSize(
        CDtcInstanceConfig *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int *a5)
{
  int v9; // ebx
  __int64 v10; // r9
  const wchar_t *v11; // rax
  __int64 v13; // [rsp+28h] [rbp-70h]
  const wchar_t *v14; // [rsp+30h] [rbp-68h]
  __int64 v15; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v16[8]; // [rsp+58h] [rbp-40h] BYREF

  v15 = 0;
  v16[0] = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    376,
    L"CDtcInstanceConfig::SetLogPathAndSize",
    0,
    L"In");
  if ( !a5 )
  {
    v14 = L"Invalid arguments.";
    v9 = -2147024809;
    LODWORD(v13) = -2147024809;
    v10 = 382;
LABEL_3:
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      v10,
      L"CDtcInstanceConfig::SetLogPathAndSize",
      v13,
      v14);
    goto LABEL_25;
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 28LL) )
  {
    v9 = -2147024846;
    v14 = L"SetLogPathAndSize is not supported on a remote host";
    v10 = 388;
    LODWORD(v13) = -2147024846;
    goto LABEL_3;
  }
  v9 = CDtcInstanceConfig::VerifyLogPathSettings(this, a2);
  if ( v9 < 0 )
  {
    v10 = 395;
    v14 = L"VerifyLogPathSettings failed";
    LODWORD(v13) = v9;
    goto LABEL_3;
  }
  if ( a4 < 1 )
  {
    LODWORD(v13) = -2147024809;
    v9 = -2147024809;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      402,
      L"CDtcInstanceConfig::SetLogPathAndSize",
      v13,
      L"i_cbMaxLogSize = %d is invalid",
      a4);
    goto LABEL_25;
  }
  if ( a3 < 1 || a3 > a4 )
  {
    LODWORD(v13) = -2147024809;
    v9 = -2147024809;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
      409,
      L"CDtcInstanceConfig::SetLogPathAndSize",
      v13,
      L"i_cbLogSize = %d is invalid, MaxLogSize = %d",
      a3,
      a4);
  }
  else
  {
    v9 = CDtcInstanceConfig::InitializeLog(this, a2, a3, a5);
    if ( v9 < 0 )
    {
      v11 = L"InitializeLog failed.";
      v10 = 416;
LABEL_14:
      v14 = v11;
      LODWORD(v13) = v9;
      goto LABEL_3;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 144LL))(
           *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
           0,
           &v15);
    if ( v9 < 0 )
    {
      v11 = L"Failed to get TM contacts.";
      v10 = 423;
      goto LABEL_14;
    }
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v15)(v15, &IID_ICustomProperties, v16);
    if ( v9 < 0 )
    {
      v11 = L"Failed to get CustomProperties from TM contacts.";
      v10 = 431;
      goto LABEL_14;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v16[0] + 80LL))(
           v16[0],
           L"LOG",
           L"Size",
           (unsigned int)a3);
    if ( v9 < 0 )
    {
      v11 = L"Failed to write log size in the registry.";
      v10 = 440;
      goto LABEL_14;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 104LL))(
           *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
           a2);
    if ( v9 < 0 )
    {
      v11 = L"Failed to set log file path.";
      v10 = 447;
      goto LABEL_14;
    }
    if ( a4 != (*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                              + 8LL)
                                                                                + 344LL))(
                 *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                 L"MaxLogSize",
                 512) )
      (*(void (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 368LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
        L"MaxLogSize",
        (unsigned int)a4);
  }
LABEL_25:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16[0] + 16LL))(v16[0]);
    v16[0] = 0;
  }
  LODWORD(v13) = v9;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinstanceconfig.cpp",
    465,
    L"CDtcInstanceConfig::SetLogPathAndSize",
    v13,
    L"Out");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004b750  mov     r11, rsp
0x18004b753  push    rbx
0x18004b754  push    rbp
0x18004b755  push    rsi
0x18004b756  push    rdi
0x18004b757  push    r14
0x18004b759  push    r15
0x18004b75b  sub     rsp, 68h
0x18004b75f  mov     r15, rdx
0x18004b762  mov     qword ptr [r11-48h], 0
0x18004b76a  mov     edx, 6
0x18004b76f  mov     qword ptr [r11-40h], 0
0x18004b777  lea     rax, aIn_0; "In"
0x18004b77e  mov     ebp, r9d
0x18004b781  mov     [r11-68h], rax
0x18004b785  lea     rdi, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004b78c  mov     r14d, r8d
0x18004b78f  mov     qword ptr [r11-70h], 0
0x18004b797  mov     rsi, rcx
0x18004b79a  lea     rax, aCdtcinstanceco; "CDtcInstanceConfig::SetLogPathAndSize"
0x18004b7a1  lea     ecx, [rdx+9]
0x18004b7a4  mov     [r11-78h], rax
0x18004b7a8  mov     r9d, 178h
0x18004b7ae  mov     r8, rdi
0x18004b7b1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004b7b6  cmp     [rsp+98h+arg_20], 0
0x18004b7bf  jnz     short loc_18004B801
0x18004b7c1  mov     eax, 80070057h
0x18004b7c6  lea     rcx, aInvalidArgumen_4; "Invalid arguments."
0x18004b7cd  mov     [rsp+98h+var_68], rcx
0x18004b7d2  mov     ebx, eax
0x18004b7d4  mov     dword ptr [rsp+98h+var_70], eax
0x18004b7d8  mov     r9d, 17Eh
0x18004b7de  mov     r8, rdi
0x18004b7e1  mov     edx, 1
0x18004b7e6  lea     rsi, aCdtcinstanceco; "CDtcInstanceConfig::SetLogPathAndSize"
0x18004b7ed  mov     ecx, 0Fh
0x18004b7f2  mov     [rsp+98h+var_78], rsi
0x18004b7f7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004b7fc  jmp     loc_18004BA0C
0x18004b801  mov     rax, [rsi+10h]
0x18004b805  cmp     dword ptr [rax+1Ch], 0
0x18004b809  jnz     short loc_18004B828
0x18004b80b  lea     rax, aSetlogpathands; "SetLogPathAndSize is not supported on a"...
0x18004b812  mov     ebx, 80070032h
0x18004b817  mov     [rsp+98h+var_68], rax
0x18004b81c  mov     r9d, 184h
0x18004b822  mov     dword ptr [rsp+98h+var_70], ebx
0x18004b826  jmp     short loc_18004B7DE
0x18004b828  mov     rdx, r15; unsigned __int16 *
0x18004b82b  mov     rcx, rsi; this
0x18004b82e  call    ?VerifyLogPathSettings@CDtcInstanceConfig@@AEAAJPEAG@Z; CDtcInstanceConfig::VerifyLogPathSettings(ushort *)
0x18004b833  mov     ebx, eax
0x18004b835  test    eax, eax
0x18004b837  jns     short loc_18004B851
0x18004b839  lea     rax, aVerifylogpaths; "VerifyLogPathSettings failed"
0x18004b840  mov     r9d, 18Bh
0x18004b846  mov     [rsp+98h+var_68], rax
0x18004b84b  mov     dword ptr [rsp+98h+var_70], ebx
0x18004b84f  jmp     short loc_18004B7DE
0x18004b851  mov     edi, 1
0x18004b856  cmp     ebp, edi
0x18004b858  jge     short loc_18004B89D
0x18004b85a  lea     rcx, aICbmaxlogsizeD; "i_cbMaxLogSize = %d is invalid"
0x18004b861  mov     [rsp+98h+var_60], ebp
0x18004b865  mov     [rsp+98h+var_68], rcx
0x18004b86a  lea     rsi, aCdtcinstanceco; "CDtcInstanceConfig::SetLogPathAndSize"
0x18004b871  mov     eax, 80070057h
0x18004b876  lea     ecx, [rdi+0Eh]
0x18004b879  mov     dword ptr [rsp+98h+var_70], eax
0x18004b87d  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004b884  mov     r9d, 192h
0x18004b88a  mov     [rsp+98h+var_78], rsi
0x18004b88f  mov     edx, edi
0x18004b891  mov     ebx, eax
0x18004b893  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004b898  jmp     loc_18004BA0C
0x18004b89d  cmp     r14d, edi
0x18004b8a0  jl      loc_18004BA88
0x18004b8a6  cmp     r14d, ebp
0x18004b8a9  jg      loc_18004BA88
0x18004b8af  mov     r9, [rsp+98h+arg_20]; unsigned int *
0x18004b8b7  mov     r8d, r14d; int
0x18004b8ba  mov     rdx, r15; unsigned __int16 *
0x18004b8bd  mov     rcx, rsi; this
0x18004b8c0  call    ?InitializeLog@CDtcInstanceConfig@@AEAAJPEAGJPEAK@Z; CDtcInstanceConfig::InitializeLog(ushort *,long,ulong *)
0x18004b8c5  mov     ebx, eax
0x18004b8c7  test    eax, eax
0x18004b8c9  jns     short loc_18004B8EF
0x18004b8cb  lea     rax, aInitializelogF; "InitializeLog failed."
0x18004b8d2  mov     r9d, 1A0h
0x18004b8d8  mov     [rsp+98h+var_68], rax
0x18004b8dd  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004b8e4  mov     dword ptr [rsp+98h+var_70], ebx
0x18004b8e8  mov     edx, edi
0x18004b8ea  jmp     loc_18004B7E6
0x18004b8ef  mov     rax, [rsi+10h]
0x18004b8f3  lea     r8, [rsp+98h+var_48]
0x18004b8f8  xor     edx, edx
0x18004b8fa  mov     rcx, [rax+8]
0x18004b8fe  mov     rax, [rcx]
0x18004b901  mov     rax, [rax+90h]
0x18004b908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b90d  mov     ebx, eax
0x18004b90f  test    eax, eax
0x18004b911  jns     short loc_18004B922
0x18004b913  lea     rax, aFailedToGetTmC; "Failed to get TM contacts."
0x18004b91a  mov     r9d, 1A7h
0x18004b920  jmp     short loc_18004B8D8
0x18004b922  mov     rcx, [rsp+98h+var_48]
0x18004b927  lea     r8, [rsp+98h+var_40]
0x18004b92c  lea     rdx, IID_ICustomProperties
0x18004b933  mov     rax, [rcx]
0x18004b936  mov     rax, [rax]
0x18004b939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b93e  mov     ebx, eax
0x18004b940  test    eax, eax
0x18004b942  jns     short loc_18004B953
0x18004b944  lea     rax, aFailedToGetCus; "Failed to get CustomProperties from TM "...
0x18004b94b  mov     r9d, 1AFh
0x18004b951  jmp     short loc_18004B8D8
0x18004b953  mov     rcx, [rsp+98h+var_40]
0x18004b958  lea     r8, aSize; "Size"
0x18004b95f  mov     r9d, r14d
0x18004b962  lea     rdx, aLog; "LOG"
0x18004b969  mov     rax, [rcx]
0x18004b96c  mov     rax, [rax+50h]
0x18004b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b975  mov     ebx, eax
0x18004b977  test    eax, eax
0x18004b979  jns     short loc_18004B98D
0x18004b97b  lea     rax, aFailedToWriteL; "Failed to write log size in the registr"...
0x18004b982  mov     r9d, 1B8h
0x18004b988  jmp     loc_18004B8D8
0x18004b98d  mov     rax, [rsi+10h]
0x18004b991  mov     rdx, r15
0x18004b994  mov     rcx, [rax+8]
0x18004b998  mov     rax, [rcx]
0x18004b99b  mov     rax, [rax+68h]
0x18004b99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9a4  mov     ebx, eax
0x18004b9a6  test    eax, eax
0x18004b9a8  jns     short loc_18004B9BC
0x18004b9aa  lea     rax, aFailedToSetLog; "Failed to set log file path."
0x18004b9b1  mov     r9d, 1BFh
0x18004b9b7  jmp     loc_18004B8D8
0x18004b9bc  mov     rax, [rsi+10h]
0x18004b9c0  lea     rdx, aMaxlogsize; "MaxLogSize"
0x18004b9c7  mov     r8d, 200h
0x18004b9cd  mov     rcx, [rax+8]
0x18004b9d1  mov     rax, [rcx]
0x18004b9d4  mov     rax, [rax+158h]
0x18004b9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9e0  cmp     ebp, eax
0x18004b9e2  jz      short loc_18004BA05
0x18004b9e4  mov     rax, [rsi+10h]
0x18004b9e8  lea     rdx, aMaxlogsize; "MaxLogSize"
0x18004b9ef  mov     r8d, ebp
0x18004b9f2  mov     rcx, [rax+8]
0x18004b9f6  mov     rax, [rcx]
0x18004b9f9  mov     rax, [rax+170h]
0x18004ba00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba05  lea     rsi, aCdtcinstanceco; "CDtcInstanceConfig::SetLogPathAndSize"
0x18004ba0c  mov     rcx, [rsp+98h+var_48]
0x18004ba11  test    rcx, rcx
0x18004ba14  jz      short loc_18004BA2B
0x18004ba16  mov     rax, [rcx]
0x18004ba19  mov     rax, [rax+10h]
0x18004ba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba22  mov     [rsp+98h+var_48], 0
0x18004ba2b  mov     rcx, [rsp+98h+var_40]
0x18004ba30  test    rcx, rcx
0x18004ba33  jz      short loc_18004BA4A
0x18004ba35  mov     rax, [rcx]
0x18004ba38  mov     rax, [rax+10h]
0x18004ba3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba41  mov     [rsp+98h+var_40], 0
0x18004ba4a  mov     edx, 6
0x18004ba4f  lea     rax, aOut; "Out"
0x18004ba56  mov     [rsp+98h+var_68], rax
0x18004ba5b  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004ba62  mov     dword ptr [rsp+98h+var_70], ebx
0x18004ba66  mov     r9d, 1D1h
0x18004ba6c  mov     [rsp+98h+var_78], rsi
0x18004ba71  lea     ecx, [rdx+9]
0x18004ba74  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004ba79  mov     eax, ebx
0x18004ba7b  add     rsp, 68h
0x18004ba7f  pop     r15
0x18004ba81  pop     r14
0x18004ba83  pop     rdi
0x18004ba84  pop     rsi
0x18004ba85  pop     rbp
0x18004ba86  pop     rbx
0x18004ba87  retn
0x18004ba88  mov     [rsp+98h+var_58], ebp
0x18004ba8c  lea     rcx, aICblogsizeDIsI; "i_cbLogSize = %d is invalid, MaxLogSize"...
0x18004ba93  mov     [rsp+98h+var_60], r14d
0x18004ba98  lea     rsi, aCdtcinstanceco; "CDtcInstanceConfig::SetLogPathAndSize"
0x18004ba9f  mov     [rsp+98h+var_68], rcx
0x18004baa4  lea     r8, aComComplusDtcD_12; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004baab  mov     eax, 80070057h
0x18004bab0  mov     ecx, 0Fh
0x18004bab5  mov     dword ptr [rsp+98h+var_70], eax
0x18004bab9  mov     r9d, 199h
0x18004babf  mov     edx, edi
0x18004bac1  mov     [rsp+98h+var_78], rsi
0x18004bac6  mov     ebx, eax
0x18004bac8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004bacd  jmp     loc_18004BA0C
```
