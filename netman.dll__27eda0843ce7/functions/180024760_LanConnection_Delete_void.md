# LanConnection::Delete(void)

- ea: `0x180024760`
- end: `0x18002490a`
- name: `?Delete@LanConnection@@UEAAJXZ`
- size: `426`
- prototype: `__int64 __fastcall(LanConnection *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001710`
- `0x180004c00`
- `0x180017560`
- `0x180024760`
- `0x18002587c`
- `0x180030324`
- `0x1800306f8`
- `0x1800317f4`
- `0x180031d0c`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024875`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024875`

## pseudocode

```c
__int64 __fastcall LanConnection::Delete(LanConnection *this)
{
  int IHNetConnection; // ebx
  bool v4; // zf
  GUID *rguid; // [rsp+20h] [rbp-E0h] BYREF
  struct IUnknown *v6; // [rsp+28h] [rbp-D8h] BYREF
  struct IUnknown *v7; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v9[264]; // [rsp+90h] [rbp-70h] BYREF

  rguid = 0;
  if ( !(unsigned int)FIsCallerNetworkConfigOpsOrAdmin() )
    return 2147943140LL;
  IHNetConnection = (*(__int64 (__fastcall **)(LanConnection *, GUID **))(*(_QWORD *)this + 56LL))(this, &rguid);
  if ( IHNetConnection >= 0 )
  {
    if ( *(_DWORD *)&rguid[2].Data2 == 7 )
    {
      v4 = *((_DWORD *)this + 24) == 0;
      v6 = 0;
      v7 = 0;
      if ( v4 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      IHNetConnection = LanConnection::HrGetIHNetConnection(this, (struct IHNetConnection **)&v6);
      if ( IHNetConnection >= 0 )
      {
        IHNetConnection = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v6->lpVtbl[2].Release)(
                            v6,
                            &GUID_85d18b75_3032_11d4_9348_00c04f8eeb71,
                            &v7);
        ReleaseObj(v6);
        if ( IHNetConnection >= 0 )
        {
          IHNetConnection = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v7->lpVtbl[1].Release)(v7, 0);
          ReleaseObj(v7);
          if ( IHNetConnection >= 0 && StringFromGUID2(rguid, sz, 39) )
          {
            StringCchCopyW(
              v9,
              0x104u,
              L"System\\CurrentControlSet\\Control\\Network\\{4D36E972-E325-11CE-BFC1-08002bE10318}");
            StringCchCatW(v9, 0x104u, L"\\");
            StringCchCatW(v9, 0x104u, sz);
            IHNetConnection = HrRegDeleteKeyTree(HKEY_LOCAL_MACHINE, v9);
            if ( IHNetConnection == -2147024894 )
              IHNetConnection = 0;
          }
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
      }
    }
    else
    {
      IHNetConnection = -2147467259;
    }
    FreeNetconProperties((struct tagNETCON_PROPERTIES *)rguid);
  }
  return (unsigned int)IHNetConnection;
}

```

## disassembly

```asm
0x180024760  mov     [rsp-8+arg_8], rbx
0x180024765  mov     [rsp-8+arg_10], rdi
0x18002476a  push    rbp
0x18002476b  lea     rbp, [rsp-1B0h]
0x180024773  sub     rsp, 2B0h
0x18002477a  mov     rax, cs:__security_cookie
0x180024781  xor     rax, rsp
0x180024784  mov     [rbp+1B0h+var_10], rax
0x18002478b  mov     rdi, rcx
0x18002478e  mov     [rsp+2B0h+rguid], 0
0x180024797  call    ?FIsCallerNetworkConfigOpsOrAdmin@@YAHXZ; FIsCallerNetworkConfigOpsOrAdmin(void)
0x18002479c  test    eax, eax
0x18002479e  jnz     short loc_1800247AA
0x1800247a0  mov     eax, 800702E4h
0x1800247a5  jmp     loc_1800248E6
0x1800247aa  mov     rax, [rdi]
0x1800247ad  lea     rdx, [rsp+2B0h+rguid]
0x1800247b2  mov     rcx, rdi
0x1800247b5  mov     rax, [rax+38h]
0x1800247b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247be  mov     ebx, eax
0x1800247c0  test    eax, eax
0x1800247c2  js      loc_1800248E4
0x1800247c8  mov     rax, [rsp+2B0h+rguid]
0x1800247cd  cmp     dword ptr [rax+24h], 7
0x1800247d1  jnz     loc_1800248D5
0x1800247d7  cmp     dword ptr [rdi+60h], 0
0x1800247db  mov     [rsp+2B0h+var_288], 0
0x1800247e4  mov     [rsp+2B0h+var_280], 0
0x1800247ed  jnz     short loc_1800247F4
0x1800247ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800247f4  lea     rdx, [rsp+2B0h+var_288]; struct IHNetConnection **
0x1800247f9  mov     rcx, rdi; this
0x1800247fc  call    ?HrGetIHNetConnection@LanConnection@@AEAAJPEAPEAUIHNetConnection@@@Z; LanConnection::HrGetIHNetConnection(IHNetConnection * *)
0x180024801  mov     ebx, eax
0x180024803  test    eax, eax
0x180024805  js      loc_1800248DA
0x18002480b  mov     rcx, [rsp+2B0h+var_288]
0x180024810  lea     r8, [rsp+2B0h+var_280]
0x180024815  lea     rdx, _GUID_85d18b75_3032_11d4_9348_00c04f8eeb71
0x18002481c  mov     rax, [rcx]
0x18002481f  mov     rax, [rax+40h]
0x180024823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024828  mov     rcx, [rsp+2B0h+var_288]; struct IUnknown *
0x18002482d  mov     ebx, eax
0x18002482f  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180024834  test    ebx, ebx
0x180024836  jns     short loc_180024842
0x180024838  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002483d  jmp     loc_1800248DA
0x180024842  mov     rcx, [rsp+2B0h+var_280]
0x180024847  xor     edx, edx
0x180024849  mov     rax, [rcx]
0x18002484c  mov     rax, [rax+28h]
0x180024850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024855  mov     rcx, [rsp+2B0h+var_280]; struct IUnknown *
0x18002485a  mov     ebx, eax
0x18002485c  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180024861  test    ebx, ebx
0x180024863  js      short loc_1800248DA
0x180024865  mov     rcx, [rsp+2B0h+rguid]; rguid
0x18002486a  lea     rdx, [rsp+2B0h+sz]; lpsz
0x18002486f  mov     r8d, 27h ; '''; cchMax
0x180024875  call    cs:__imp_StringFromGUID2
0x18002487b  test    eax, eax
0x18002487d  jz      short loc_1800248DA
0x18002487f  mov     ebx, 104h
0x180024884  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Net"...
0x18002488b  mov     edx, ebx; unsigned __int64
0x18002488d  lea     rcx, [rbp+1B0h+var_220]; unsigned __int16 *
0x180024891  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024896  lea     r8, asc_18003AB20; "\\"
0x18002489d  mov     edx, ebx; unsigned __int64
0x18002489f  lea     rcx, [rbp+1B0h+var_220]; unsigned __int16 *
0x1800248a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800248a8  lea     r8, [rsp+2B0h+sz]; unsigned __int16 *
0x1800248ad  mov     edx, ebx; unsigned __int64
0x1800248af  lea     rcx, [rbp+1B0h+var_220]; unsigned __int16 *
0x1800248b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800248b8  lea     rdx, [rbp+1B0h+var_220]; unsigned __int16 *
0x1800248bc  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800248c3  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x1800248c8  mov     ebx, eax
0x1800248ca  cmp     eax, 80070002h
0x1800248cf  jnz     short loc_1800248DA
0x1800248d1  xor     ebx, ebx
0x1800248d3  jmp     short loc_1800248DA
0x1800248d5  mov     ebx, 80004005h
0x1800248da  mov     rcx, [rsp+2B0h+rguid]; pv
0x1800248df  call    ?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetconProperties(tagNETCON_PROPERTIES *)
0x1800248e4  mov     eax, ebx
0x1800248e6  mov     rcx, [rbp+1B0h+var_10]
0x1800248ed  xor     rcx, rsp; StackCookie
0x1800248f0  call    __security_check_cookie
0x1800248f5  lea     r11, [rsp+2B0h+var_s0]
0x1800248fd  mov     rbx, [r11+18h]
0x180024901  mov     rdi, [r11+20h]
0x180024905  mov     rsp, r11
0x180024908  pop     rbp
0x180024909  retn
```
