# CKsProxy::DllInitClassesKsProxy(int,_GUID const *)

- ea: `0x10008190`
- end: `0x10008238`
- name: `?DllInitClassesKsProxy@CKsProxy@@SGXHPBU_GUID@@@Z`
- size: `168`
- prototype: `void __stdcall(int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x10005ef6`
- `0x10006775`
- `0x100067c8`
- `0x10008190`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x10008229`
- `ADVAPI32!EventUnregister` at `0x10008229`

## pseudocode

```c
void __stdcall CKsProxy::DllInitClassesKsProxy(int a1, const struct _GUID *a2)
{
  int v2; // ecx
  int v3; // ecx
  REGHANDLE v4; // [esp-8h] [ebp-28h]
  GUID v5; // [esp+10h] [ebp-10h]

  v2 = 0;
  v5 = _GUID_17cca71b_ecd7_11d0_b908_00a0c9223196;
  while ( *(&v5.Data1 + v2) == *(&a2->Data1 + v2) )
  {
    if ( ++v2 == 4 )
    {
      if ( a1 )
      {
        dword_1003D2D8 = 0;
        WPP_MAIN_CB = 0;
        dword_1003D2E0 = 1;
        dword_1003D2E4 = 0;
        WPP_REGISTRATION_GUIDS = (int)WPP_ThisDir_CTLGUID_KsProxyWPP;
        WPP_GLOBAL_Control = &WPP_MAIN_CB;
        WppInitUm();
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
      }
      else
      {
        WppCleanupUm();
        v4 = RegHandle;
        dword_1003D0A0 = 0;
        RegHandle = 0;
        EventUnregister(v4);
      }
      return;
    }
  }
}

```

## disassembly

```asm
0x10008190  mov     edi, edi
0x10008192  push    ebp
0x10008193  mov     ebp, esp
0x10008195  and     esp, 0FFFFFFF8h
0x10008198  sub     esp, 14h
0x1000819b  mov     edx, [ebp+arg_4]
0x1000819e  push    ebx
0x1000819f  push    esi
0x100081a0  push    edi
0x100081a1  mov     esi, offset __GUID_17cca71b_ecd7_11d0_b908_00a0c9223196
0x100081a6  lea     edi, [esp+20h+var_10]
0x100081aa  xor     ebx, ebx
0x100081ac  mov     ecx, ebx
0x100081ae  movsd
0x100081af  movsd
0x100081b0  movsd
0x100081b1  movsd
0x100081b2  lea     esi, [esp+20h+var_10]
0x100081b6  mov     eax, [esi+ecx*4]
0x100081b9  cmp     eax, [edx+ecx*4]
0x100081bc  jnz     short loc_1000822F
0x100081be  inc     ecx
0x100081bf  cmp     ecx, 4
0x100081c2  jnz     short loc_100081B6
0x100081c4  cmp     [ebp+arg_0], ebx
0x100081c7  jz      short loc_10008206
0x100081c9  mov     dword_1003D2D8, ebx
0x100081cf  mov     _WPP_MAIN_CB, ebx
0x100081d5  mov     dword_1003D2E0, 1
0x100081df  mov     dword_1003D2E4, ebx
0x100081e5  mov     _WPP_REGISTRATION_GUIDS, offset _WPP_ThisDir_CTLGUID_KsProxyWPP
0x100081ef  mov     _WPP_GLOBAL_Control, offset _WPP_MAIN_CB
0x100081f9  call    _WppInitUm@4; WppInitUm(x)
0x100081fe  push    ecx
0x100081ff  call    _TraceLoggingRegisterEx_EventRegister_EventSetInformation@12; TraceLoggingRegisterEx_EventRegister_EventSetInformation(x,x,x)
0x10008204  jmp     short loc_1000822F
0x10008206  call    _WppCleanupUm@0; WppCleanupUm()
0x1000820b  mov     eax, dword ptr RegHandle+4
0x10008210  xorps   xmm0, xmm0
0x10008213  mov     ecx, dword ptr RegHandle
0x10008219  push    eax
0x1000821a  push    ecx; RegHandle
0x1000821b  mov     dword_1003D0A0, ebx
0x10008221  movlpd  RegHandle, xmm0
0x10008229  call    ds:__imp__EventUnregister@8; EventUnregister(x,x)
0x1000822f  pop     edi
0x10008230  pop     esi
0x10008231  pop     ebx
0x10008232  mov     esp, ebp
0x10008234  pop     ebp
0x10008235  retn    8
```
