# FwRemoteAdminSettings::get_RemoteAddresses(ushort * *)

- ea: `0x180047810`
- end: `0x1800478f7`
- name: `?get_RemoteAddresses@FwRemoteAdminSettings@@UEAAJPEAPEAG@Z`
- size: `231`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x180047304`
- `0x1800474c8`
- `0x180047810`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x1800478a0`
- `fwbase!FwReportReturnError` at `0x1800478c6`
- `fwbase!FwReportReturnError` at `0x1800478a0`
- `fwbase!FwReportReturnError` at `0x1800478c6`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180047889`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180047889`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800478b1`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x1800478b1`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::get_RemoteAddresses(FwRemoteAdminSettings *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int RemoteAddrs; // eax
  _BYTE v8[80]; // [rsp+20h] [rbp-78h] BYREF

  memset_0(v8, 0, 0x48u);
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_7:
    FwReportReturnError("FwRemoteAdminSettings::get_RemoteAddresses", v5);
    goto LABEL_8;
  }
  *a2 = 0;
  RemoteAddrs = FwRemoteAdminSettings::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwRemoteAdminSettings::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8),
        v4 = RemoteAddrs,
        RemoteAddrs < 0)
    || (RemoteAddrs = GetOpenPortorAuthAppAsBSTR(v8, a2), v4 = RemoteAddrs, RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_7;
  }
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047810  mov     [rsp+arg_10], rbx
0x180047815  push    rbp
0x180047816  push    rsi
0x180047817  push    rdi
0x180047818  sub     rsp, 80h
0x18004781f  mov     rax, cs:__security_cookie
0x180047826  xor     rax, rsp
0x180047829  mov     [rsp+98h+var_28], rax
0x18004782e  mov     rdi, rdx
0x180047831  mov     rsi, rcx
0x180047834  xor     edx, edx; Val
0x180047836  lea     rcx, [rsp+98h+var_78]; void *
0x18004783b  lea     r8d, [rdx+48h]; Size
0x18004783f  call    memset_0
0x180047844  lea     rbp, aFwremoteadmins; "FwRemoteAdminSettings::get_RemoteAddres"...
0x18004784b  test    rdi, rdi
0x18004784e  jnz     short loc_180047859
0x180047850  mov     ebx, 80004003h
0x180047855  mov     edx, ebx
0x180047857  jmp     short loc_18004789D
0x180047859  mov     rcx, rsi; this
0x18004785c  mov     qword ptr [rdi], 0
0x180047863  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x180047868  mov     ebx, eax
0x18004786a  test    eax, eax
0x18004786c  js      short loc_18004789B
0x18004786e  lea     rdx, [rsp+98h+var_78]; struct _tag_FW_ADDRESSES *
0x180047873  mov     rcx, rsi; this
0x180047876  call    ?GetRemoteAddrs@FwRemoteAdminSettings@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x18004787b  mov     ebx, eax
0x18004787d  test    eax, eax
0x18004787f  js      short loc_18004789B
0x180047881  mov     rdx, rdi
0x180047884  lea     rcx, [rsp+98h+var_78]
0x180047889  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x180047890  nop     dword ptr [rax+rax+00h]
0x180047895  mov     ebx, eax
0x180047897  test    eax, eax
0x180047899  jns     short loc_1800478AC
0x18004789b  mov     edx, eax
0x18004789d  mov     rcx, rbp
0x1800478a0  call    cs:__imp_FwReportReturnError
0x1800478a7  nop     dword ptr [rax+rax+00h]
0x1800478ac  lea     rcx, [rsp+98h+var_78]
0x1800478b1  call    cs:__imp_FwPolioEmptyWFAddresses
0x1800478b8  nop     dword ptr [rax+rax+00h]
0x1800478bd  test    ebx, ebx
0x1800478bf  jns     short loc_1800478D4
0x1800478c1  mov     edx, ebx
0x1800478c3  mov     rcx, rbp
0x1800478c6  call    cs:__imp_FwReportReturnError
0x1800478cd  nop     dword ptr [rax+rax+00h]
0x1800478d2  mov     ebx, eax
0x1800478d4  mov     eax, ebx
0x1800478d6  mov     rcx, [rsp+98h+var_28]
0x1800478db  xor     rcx, rsp; StackCookie
0x1800478de  call    __security_check_cookie
0x1800478e3  mov     rbx, [rsp+98h+arg_10]
0x1800478eb  add     rsp, 80h
0x1800478f2  pop     rdi
0x1800478f3  pop     rsi
0x1800478f4  pop     rbp
0x1800478f5  retn
```
