# OdmlSvcStartInstallUpdate

- ea: `0x180008690`
- end: `0x18000875f`
- name: `OdmlSvcStartInstallUpdate`
- size: `207`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001d00`
- `0x180007298`
- `0x180008690`
- `0x18000d010`

## import_xrefs

- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800086ca`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x1800086ca`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000871b`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000871b`

## string_xrefs

- `0x1800086b8`: `[MosHost] OdmlSvcStartInstallUpdate`
- `0x1800086bf`: `OdmlSvcStartInstallUpdate`
- `0x180008712`: `OdmlSvcStartInstallUpdate`

## pseudocode

```c
__int64 __fastcall OdmlSvcStartInstallUpdate(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // ebx
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-28h] BYREF

  if ( dword_1800185C4 != a1 )
    __int2c();
  ZTraceHelperNoThis(3, "OdmlSvcStartInstallUpdate", 127, "[MosHost] OdmlSvcStartInstallUpdate");
  if ( (Microsoft_Windows_MosHostEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v1, (const EVENT_DESCRIPTOR *)StartInstallationStart, v2, 1u, &v8);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1800185D0 + 24LL))(qword_1800185D0);
  if ( v3 >= 0 )
  {
    v6 = 0;
    if ( (Microsoft_Windows_MosHostEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v4, (const EVENT_DESCRIPTOR *)StartInstallationStop, v5, 1u, &v8);
  }
  else
  {
    return (unsigned int)ZTraceReportPropagationNoThis(v3, "OdmlSvcStartInstallUpdate", 131);
  }
  return v6;
}

```

## disassembly

```asm
0x180008690  push    rbx
0x180008692  sub     rsp, 50h
0x180008696  mov     rax, cs:__security_cookie
0x18000869d  xor     rax, rsp
0x1800086a0  mov     [rsp+58h+var_18], rax
0x1800086a5  mov     eax, cs:dword_1800185C4
0x1800086ab  nop
0x1800086ac  cmp     eax, ecx
0x1800086ae  jz      short loc_1800086B2
0x1800086b0  int     2Ch; Windows NT - assertion failure
0x1800086b2  mov     r8d, 7Fh
0x1800086b8  lea     r9, aMoshostOdmlsvc_15; "[MosHost] OdmlSvcStartInstallUpdate"
0x1800086bf  lea     rdx, aOdmlsvcstartin; "OdmlSvcStartInstallUpdate"
0x1800086c6  lea     ecx, [r8-7Ch]
0x1800086ca  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x1800086d0  test    cs:Microsoft_Windows_MosHostEnableBits, 4
0x1800086d7  jz      short loc_1800086F5
0x1800086d9  lea     rax, [rsp+58h+var_28]
0x1800086de  mov     r9d, 1
0x1800086e4  lea     rdx, StartInstallationStart
0x1800086eb  mov     [rsp+58h+var_38], rax
0x1800086f0  call    McGenEventWrite_EventWriteTransfer
0x1800086f5  mov     rcx, cs:qword_1800185D0
0x1800086fc  mov     rax, [rcx]
0x1800086ff  mov     rax, [rax+18h]
0x180008703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008708  test    eax, eax
0x18000870a  jns     short loc_180008725
0x18000870c  mov     r8d, 83h
0x180008712  lea     rdx, aOdmlsvcstartin; "OdmlSvcStartInstallUpdate"
0x180008719  mov     ecx, eax
0x18000871b  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008721  mov     ebx, eax
0x180008723  jmp     short loc_18000874A
0x180008725  xor     ebx, ebx
0x180008727  test    cs:Microsoft_Windows_MosHostEnableBits, 4
0x18000872e  jz      short loc_18000874A
0x180008730  lea     rax, [rsp+58h+var_28]
0x180008735  lea     r9d, [rbx+1]
0x180008739  mov     [rsp+58h+var_38], rax
0x18000873e  lea     rdx, StartInstallationStop
0x180008745  call    McGenEventWrite_EventWriteTransfer
0x18000874a  mov     eax, ebx
0x18000874c  mov     rcx, [rsp+58h+var_18]
0x180008751  xor     rcx, rsp; StackCookie
0x180008754  call    __security_check_cookie
0x180008759  add     rsp, 50h
0x18000875d  pop     rbx
0x18000875e  retn
```
