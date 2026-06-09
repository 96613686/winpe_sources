# BluetoothConnection::HrInit(void *,_SP_DEVINFO_DATA *,ushort *)

- ea: `0x180029128`
- end: `0x180029265`
- name: `?HrInit@BluetoothConnection@@AEAAJPEAXPEAU_SP_DEVINFO_DATA@@PEAG@Z`
- size: `317`
- prototype: `__int64 __fastcall(BluetoothConnection *this, void *, struct _SP_DEVINFO_DATA *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800275bc`
- `0x180029600`
- `0x180029ab0`

## callees

- `0x180001710`
- `0x18000538c`
- `0x180028d38`
- `0x180029128`
- `0x180029424`
- `0x1800345e8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800291e5`
- `ADVAPI32!RegCloseKey` at `0x1800291e5`
- `KERNEL32!GetLastError` at `0x1800291a3`
- `KERNEL32!GetLastError` at `0x1800291a3`
- `KERNEL32!CreateEventW` at `0x180029191`
- `KERNEL32!CreateEventW` at `0x180029191`
- `KERNEL32!CloseHandle` at `0x1800291fd`
- `KERNEL32!CloseHandle` at `0x1800291fd`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::HrInit(
        BluetoothConnection *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        unsigned __int16 *a4)
{
  signed int NetCfgInstGuid; // ebx
  HANDLE EventW; // rax
  BluetoothConnection *v8; // rcx
  int v9; // r8d
  signed int LastError; // eax
  HKEY *v11; // rsi
  int ConnectionKey; // eax
  BluetoothConnection *v13; // rcx
  struct _GUID v15; // [rsp+20h] [rbp-48h] BYREF

  *((_QWORD *)this + 14) = a2;
  v15 = 0;
  *(struct _SP_DEVINFO_DATA *)((char *)this + 120) = *a3;
  NetCfgInstGuid = HrGetNetCfgInstGuid(a2, a3, &v15);
  if ( !NetCfgInstGuid )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 19) = EventW;
    if ( EventW )
    {
      v11 = (HKEY *)((char *)this + 96);
      ConnectionKey = BluetoothConnection::HrGetConnectionKey(v8, &v15, v9, (HKEY *)this + 12);
      NetCfgInstGuid = ConnectionKey;
      if ( ConnectionKey )
      {
        if ( ConnectionKey >= 0 )
          goto LABEL_10;
      }
      else
      {
        NetCfgInstGuid = BluetoothConnection::HrUpdateConnectionInfo(v13, a4, *v11);
        if ( NetCfgInstGuid >= 0 )
          goto LABEL_10;
        RegCloseKey(*v11);
        *v11 = 0;
      }
      CloseHandle(*((HANDLE *)this + 19));
      *((_QWORD *)this + 19) = 0;
      goto LABEL_10;
    }
    LastError = GetLastError();
    NetCfgInstGuid = LastError;
    if ( LastError > 0 )
      NetCfgInstGuid = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_10:
  *((_DWORD *)this + 26) = NetCfgInstGuid == 0;
  if ( NetCfgInstGuid < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids,
      (unsigned int)NetCfgInstGuid);
  return (unsigned int)NetCfgInstGuid;
}

```

## disassembly

```asm
0x180029128  push    rbx
0x18002912a  push    rbp
0x18002912b  push    rsi
0x18002912c  push    rdi
0x18002912d  sub     rsp, 48h
0x180029131  mov     rax, cs:__security_cookie
0x180029138  xor     rax, rsp
0x18002913b  mov     [rsp+68h+var_38], rax
0x180029140  mov     [rcx+70h], rdx
0x180029144  xorps   xmm0, xmm0
0x180029147  mov     rax, rdx
0x18002914a  mov     rbp, r9
0x18002914d  mov     r9, r8
0x180029150  mov     rdi, rcx
0x180029153  movups  xmmword ptr [rsp+68h+var_48.Data1], xmm0
0x180029158  mov     rdx, r9; struct _SP_DEVINFO_DATA *
0x18002915b  movups  xmm0, xmmword ptr [r8]
0x18002915f  movups  xmmword ptr [rcx+78h], xmm0
0x180029163  movups  xmm1, xmmword ptr [r8+10h]
0x180029168  lea     r8, [rsp+68h+var_48]; struct _GUID *
0x18002916d  movups  xmmword ptr [rcx+88h], xmm1
0x180029174  mov     rcx, rax; void *
0x180029177  call    ?HrGetNetCfgInstGuid@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_GUID@@@Z; HrGetNetCfgInstGuid(void *,_SP_DEVINFO_DATA *,_GUID *)
0x18002917c  mov     ebx, eax
0x18002917e  test    eax, eax
0x180029180  jnz     loc_18002920E
0x180029186  xor     r9d, r9d; lpName
0x180029189  lea     edx, [rax+1]; bManualReset
0x18002918c  xor     r8d, r8d; bInitialState
0x18002918f  xor     ecx, ecx; lpEventAttributes
0x180029191  call    cs:__imp_CreateEventW
0x180029197  mov     [rdi+98h], rax
0x18002919e  test    rax, rax
0x1800291a1  jnz     short loc_1800291BA
0x1800291a3  call    cs:__imp_GetLastError
0x1800291a9  mov     ebx, eax
0x1800291ab  test    eax, eax
0x1800291ad  jle     short loc_18002920E
0x1800291af  movzx   ebx, ax
0x1800291b2  or      ebx, 80070000h
0x1800291b8  jmp     short loc_18002920E
0x1800291ba  lea     rsi, [rdi+60h]
0x1800291be  mov     r9, rsi; HKEY *
0x1800291c1  lea     rdx, [rsp+68h+var_48]; struct _GUID *
0x1800291c6  call    ?HrGetConnectionKey@BluetoothConnection@@AEAAJPEBU_GUID@@HPEAPEAUHKEY__@@@Z; BluetoothConnection::HrGetConnectionKey(_GUID const *,int,HKEY__ * *)
0x1800291cb  mov     ebx, eax
0x1800291cd  test    eax, eax
0x1800291cf  jnz     short loc_1800291F4
0x1800291d1  mov     r8, [rsi]; HKEY
0x1800291d4  mov     rdx, rbp; unsigned __int16 *
0x1800291d7  call    ?HrUpdateConnectionInfo@BluetoothConnection@@AEAAJPEAGPEAUHKEY__@@@Z; BluetoothConnection::HrUpdateConnectionInfo(ushort *,HKEY__ *)
0x1800291dc  mov     ebx, eax
0x1800291de  test    eax, eax
0x1800291e0  jns     short loc_18002920E
0x1800291e2  mov     rcx, [rsi]; hKey
0x1800291e5  call    cs:__imp_RegCloseKey
0x1800291eb  mov     qword ptr [rsi], 0
0x1800291f2  jmp     short loc_1800291F6
0x1800291f4  jns     short loc_18002920E
0x1800291f6  mov     rcx, [rdi+98h]; hObject
0x1800291fd  call    cs:__imp_CloseHandle
0x180029203  mov     qword ptr [rdi+98h], 0
0x18002920e  xor     eax, eax
0x180029210  test    ebx, ebx
0x180029212  setz    al
0x180029215  mov     [rdi+68h], eax
0x180029218  test    ebx, ebx
0x18002921a  jns     short loc_18002924D
0x18002921c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029223  lea     rax, WPP_GLOBAL_Control
0x18002922a  cmp     rcx, rax
0x18002922d  jz      short loc_18002924D
0x18002922f  test    byte ptr [rcx+1Ch], 1
0x180029233  jz      short loc_18002924D
0x180029235  mov     rcx, [rcx+10h]
0x180029239  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180029240  mov     edx, 11h
0x180029245  mov     r9d, ebx
0x180029248  call    WPP_SF_d
0x18002924d  mov     eax, ebx
0x18002924f  mov     rcx, [rsp+68h+var_38]
0x180029254  xor     rcx, rsp; StackCookie
0x180029257  call    __security_check_cookie
0x18002925c  add     rsp, 48h
0x180029260  pop     rdi
0x180029261  pop     rsi
0x180029262  pop     rbp
0x180029263  pop     rbx
0x180029264  retn
```
