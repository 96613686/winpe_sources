# SSFDoneWithSession(ISAPI_CONTEXT *,ulong *)

- ea: `0x1800068bc`
- end: `0x180006969`
- name: `?SSFDoneWithSession@@YAJPEAVISAPI_CONTEXT@@PEAK@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e34`
- `0x1800068bc`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000691b`
- `iisutil!PuDbgPrint` at `0x18000691b`

## string_xrefs

- `0x180006914`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFDoneWithSession(struct ISAPI_CONTEXT *this, unsigned int *a2)
{
  __int64 v3; // rsi

  v3 = *((_QWORD *)this + 24);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      933,
      "SSFDoneWithSession",
      "\r\n  HSE_REQ_DONE_WITH_SESSION[%p]: Function Entry\r\n  <END>\r\n\r\n",
      this);
  if ( a2 && *a2 == 2 && *((_DWORD *)this + 62) )
  {
    *((_DWORD *)this + 63) = 1;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, 0);
  }
  ISAPI_CONTEXT::DereferenceIsapiContext(this);
  return 0;
}

```

## disassembly

```asm
0x1800068bc  mov     r11, rsp
0x1800068bf  mov     [r11+8], rbx
0x1800068c3  mov     [r11+10h], rsi
0x1800068c7  push    rdi
0x1800068c8  sub     rsp, 30h
0x1800068cc  mov     eax, cs:g_dwDebugFlags
0x1800068d2  mov     rdi, rdx
0x1800068d5  mov     rsi, [rcx+0C0h]
0x1800068dc  test    al, 3
0x1800068de  mov     rbx, rcx
0x1800068e1  setnz   r8b
0x1800068e5  bt      eax, 1Ah
0x1800068e9  setb    al
0x1800068ec  test    al, r8b
0x1800068ef  jz      short loc_180006921
0x1800068f1  mov     [r11-10h], rcx
0x1800068f5  lea     rax, aHseReqDoneWith; "\r\n  HSE_REQ_DONE_WITH_SESSION[%p]: Fu"...
0x1800068fc  mov     rcx, cs:g_pDebug
0x180006903  lea     r9, aSsfdonewithses; "SSFDoneWithSession"
0x18000690a  mov     r8d, 3A5h
0x180006910  mov     [r11-18h], rax
0x180006914  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000691b  call    cs:__imp_PuDbgPrint
0x180006921  test    rdi, rdi
0x180006924  jz      short loc_18000694F
0x180006926  cmp     dword ptr [rdi], 2
0x180006929  jnz     short loc_18000694F
0x18000692b  cmp     dword ptr [rbx+0F8h], 0
0x180006932  jz      short loc_18000694F
0x180006934  mov     dword ptr [rbx+0FCh], 1
0x18000693e  xor     edx, edx
0x180006940  mov     rax, [rsi]
0x180006943  mov     rcx, rsi
0x180006946  mov     rax, [rax+38h]
0x18000694a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694f  mov     rcx, rbx; this
0x180006952  call    ?DereferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::DereferenceIsapiContext(void)
0x180006957  mov     rbx, [rsp+38h+arg_0]
0x18000695c  xor     eax, eax
0x18000695e  mov     rsi, [rsp+38h+arg_8]
0x180006963  add     rsp, 30h
0x180006967  pop     rdi
0x180006968  retn
```
