# DockingDevnodeHelpers::GetAepProperties(ushort const *,_GUID const &,char const &,char const &,char const &,char const &,ushort const *,ulong,_DEVPROPERTY *,ulong *)

- ea: `0x18000de64`
- end: `0x18000e2a5`
- name: `?GetAepProperties@DockingDevnodeHelpers@@SAJPEBGAEBU_GUID@@AEBD2220KPEAU_DEVPROPERTY@@PEAK@Z`
- size: `1089`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, char *, const char *, char *, char *, unsigned __int16 *, unsigned int, struct _DEVPROPERTY *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009660`
- `0x18000f3ec`
- `0x180012ddc`
- `0x180018be0`

## callees

- `0x18000de64`
- `0x18000fedc`
- `0x18000ff04`

## pseudocode

```c
__int64 __fastcall DockingDevnodeHelpers::GetAepProperties(
        unsigned __int16 *a1,
        struct _GUID *a2,
        char *a3,
        const char *a4,
        char *a5,
        char *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        struct _DEVPROPERTY *a9,
        unsigned int *a10)
{
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx

  a9->CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9->CompKey.Key = DEVPKEY_Device_FriendlyName;
  v12 = -1;
  a9->Type = 18;
  do
    ++v12;
  while ( a1[v12] );
  a9[1].Buffer = a2;
  a9->BufferSize = 2 * v12 + 2;
  a9[1].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_ContainerId;
  a9[1].CompKey.Key.pid = 2;
  a9->Buffer = a1;
  a9[1].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[2].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsAssociatable;
  a9[2].CompKey.Key.pid = 3;
  a9[1].Type = 13;
  a9[1].BufferSize = 16;
  a9[3].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_FriendlyName;
  a9[3].CompKey.Key.pid = 4;
  v13 = -1;
  a9[2].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[2].Type = 17;
  a9[2].BufferSize = 1;
  a9[2].Buffer = a3;
  a9[3].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[3].Type = 18;
  do
    ++v13;
  while ( a1[v13] );
  a9[3].BufferSize = 2 * v13 + 2;
  a9[4].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_RefreshDevicePresenceState;
  a9[4].CompKey.Key.pid = 15;
  a9[3].Buffer = a1;
  a9[4].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[5].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_ModelName;
  a9[5].CompKey.Key.pid = 3;
  v14 = -1;
  a9[4].Type = 17;
  a9[4].BufferSize = 1;
  a9[4].Buffer = (PVOID)DockingDevnodeHelpers::DevPropTrue;
  a9[5].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[5].Type = 18;
  do
    ++v14;
  while ( a7[v14] );
  a9[5].BufferSize = 2 * v14 + 2;
  a9[6].CompKey.Key = DEVPKEY_DeviceContainer_IsNetworkDevice;
  a9[6].Buffer = (PVOID)DockingDevnodeHelpers::DevPropTrue;
  a9[7].CompKey.Key = DEVPKEY_DeviceContainer_IsConnected;
  a9[5].Buffer = a7;
  a9[6].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[8].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsConnected;
  a9[8].CompKey.Key.pid = 7;
  a9[6].Type = 17;
  a9[6].BufferSize = 1;
  a9[9].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_Present;
  a9[9].CompKey.Key.pid = 9;
  a9[7].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[7].Type = 17;
  a9[10].CompKey.Key.fmtid = (DEVPROPGUID)DEVPKEY_WirelessDocking_AutoConnectDisallowed;
  a9[10].CompKey.Key.pid = 1;
  a9[7].BufferSize = 1;
  a9[7].Buffer = a6;
  a9[11].CompKey.Key = DEVPKEY_NAME;
  v15 = -1;
  a9[8].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[8].Type = 17;
  a9[8].BufferSize = 1;
  a9[8].Buffer = a6;
  a9[9].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[9].Type = 17;
  a9[9].BufferSize = 1;
  a9[9].Buffer = a3;
  a9[10].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[10].Type = 17;
  a9[10].BufferSize = 1;
  a9[10].Buffer = a5;
  a9[11].CompKey.Store = DEVPROP_STORE_SYSTEM;
  a9[11].Type = 18;
  do
    ++v15;
  while ( a1[v15] );
  a9[11].Buffer = a1;
  a9[11].BufferSize = 2 * v15 + 2;
  *a10 = 12;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, 0, a1);
    v16 = WPP_GLOBAL_Control;
  }
  if ( *a3 == -1 )
  {
    if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
    {
      v17 = 46;
LABEL_22:
      WPP_SF_(v16[2], v17, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
  }
  else if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
  {
    v17 = 47;
    goto LABEL_22;
  }
  if ( *a5 == -1 )
  {
    if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
    {
      v18 = 48;
LABEL_32:
      WPP_SF_(v16[2], v18, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
  }
  else if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
  {
    v18 = 49;
    goto LABEL_32;
  }
  if ( *a6 == -1 )
  {
    if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
    {
      v19 = 50;
LABEL_42:
      WPP_SF_(v16[2], v19, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids);
    }
  }
  else if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 3u && (*((_BYTE *)v16 + 28) & 1) != 0 )
  {
    v19 = 51;
    goto LABEL_42;
  }
  return 0;
}

```

## disassembly

```asm
0x18000de64  push    rbx
0x18000de66  push    rbp
0x18000de67  push    rsi
0x18000de68  push    rdi
0x18000de69  push    r12
0x18000de6b  push    r13
0x18000de6d  push    r15
0x18000de6f  sub     rsp, 20h
0x18000de73  mov     r9, [rsp+58h+arg_40]
0x18000de7b  mov     rbx, r8
0x18000de7e  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x18000de84  xor     r8d, r8d
0x18000de87  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x18000de8e  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000de92  mov     r10, rcx
0x18000de95  mov     [r9+14h], r8d
0x18000de99  lea     r11d, [r8+12h]
0x18000de9d  movups  xmmword ptr [r9], xmm0
0x18000dea1  mov     [r9+10h], eax
0x18000dea5  mov     rax, r13
0x18000dea8  mov     [r9+20h], r11d
0x18000deac  inc     rax
0x18000deaf  cmp     [rcx+rax*2], r8w
0x18000deb4  jnz     short loc_18000DEAC
0x18000deb6  movups  xmm0, cs:DEVPKEY_Aep_ContainerId
0x18000debd  lea     eax, ds:2[rax*2]
0x18000dec4  mov     [r9+58h], rdx
0x18000dec8  mov     [r9+24h], eax
0x18000decc  mov     edx, 11h
0x18000ded1  mov     eax, cs:dword_1800212E0
0x18000ded7  movups  xmmword ptr [r9+30h], xmm0
0x18000dedc  mov     [r9+40h], eax
0x18000dee0  mov     eax, cs:dword_1800212C8
0x18000dee6  lea     ebp, [rdx-10h]
0x18000dee9  movups  xmm0, cs:DEVPKEY_Aep_IsAssociatable
0x18000def0  mov     [r9+28h], r10
0x18000def4  mov     [r9+44h], r8d
0x18000def8  movups  xmmword ptr [r9+60h], xmm0
0x18000defd  mov     [r9+70h], eax
0x18000df01  mov     eax, cs:dword_180021340
0x18000df07  movups  xmm0, cs:DEVPKEY_Aep_FriendlyName
0x18000df0e  mov     dword ptr [r9+50h], 0Dh
0x18000df16  mov     dword ptr [r9+54h], 10h
0x18000df1e  movups  xmmword ptr [r9+90h], xmm0
0x18000df26  mov     [r9+0A0h], eax
0x18000df2d  mov     rax, r13
0x18000df30  mov     [r9+74h], r8d
0x18000df34  mov     [r9+80h], edx
0x18000df3b  mov     [r9+84h], ebp
0x18000df42  mov     [r9+88h], rbx
0x18000df49  mov     [r9+0A4h], r8d
0x18000df50  mov     [r9+0B0h], r11d
0x18000df57  inc     rax
0x18000df5a  cmp     [rcx+rax*2], r8w
0x18000df5f  jnz     short loc_18000DF57
0x18000df61  movups  xmm0, cs:DEVPKEY_Aep_RefreshDevicePresenceState
0x18000df68  mov     rcx, [rsp+58h+arg_30]
0x18000df70  lea     eax, ds:2[rax*2]
0x18000df77  mov     [r9+0B4h], eax
0x18000df7e  lea     rdi, ?DevPropTrue@DockingDevnodeHelpers@@2DB; char const DockingDevnodeHelpers::DevPropTrue
0x18000df85  mov     eax, cs:dword_1800211F0
0x18000df8b  movups  xmmword ptr [r9+0C0h], xmm0
0x18000df93  mov     [r9+0D0h], eax
0x18000df9a  mov     eax, cs:dword_180021270
0x18000dfa0  movups  xmm0, cs:DEVPKEY_Aep_ModelName
0x18000dfa7  mov     [r9+0B8h], r10
0x18000dfae  mov     [r9+0D4h], r8d
0x18000dfb5  movups  xmmword ptr [r9+0F0h], xmm0
0x18000dfbd  mov     [r9+100h], eax
0x18000dfc4  mov     rax, r13
0x18000dfc7  mov     [r9+0E0h], edx
0x18000dfce  mov     [r9+0E4h], ebp
0x18000dfd5  mov     [r9+0E8h], rdi
0x18000dfdc  mov     [r9+104h], r8d
0x18000dfe3  mov     [r9+110h], r11d
0x18000dfea  inc     rax
0x18000dfed  cmp     [rcx+rax*2], r8w
0x18000dff2  jnz     short loc_18000DFEA
0x18000dff4  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsNetworkDevice.fmtid.Data1
0x18000dffb  mov     rsi, [rsp+58h+arg_28]
0x18000e003  lea     eax, ds:2[rax*2]
0x18000e00a  mov     [r9+114h], eax
0x18000e011  mov     eax, cs:DEVPKEY_DeviceContainer_IsNetworkDevice.pid
0x18000e017  movups  xmmword ptr [r9+120h], xmm0
0x18000e01f  mov     [r9+130h], eax
0x18000e026  mov     eax, cs:DEVPKEY_DeviceContainer_IsConnected.pid
0x18000e02c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18000e033  mov     [r9+148h], rdi
0x18000e03a  mov     rdi, [rsp+58h+arg_20]
0x18000e042  movups  xmmword ptr [r9+150h], xmm0
0x18000e04a  mov     [r9+160h], eax
0x18000e051  mov     eax, cs:dword_180021358
0x18000e057  movups  xmm0, cs:DEVPKEY_Aep_IsConnected
0x18000e05e  mov     [r9+118h], rcx
0x18000e065  mov     [r9+134h], r8d
0x18000e06c  movups  xmmword ptr [r9+180h], xmm0
0x18000e074  mov     [r9+190h], eax
0x18000e07b  mov     eax, cs:dword_180021158
0x18000e081  movups  xmm0, cs:DEVPKEY_Aep_Present
0x18000e088  mov     [r9+140h], edx
0x18000e08f  mov     [r9+144h], ebp
0x18000e096  movups  xmmword ptr [r9+1B0h], xmm0
0x18000e09e  mov     [r9+1C0h], eax
0x18000e0a5  mov     eax, cs:dword_180021308
0x18000e0ab  movups  xmm0, cs:DEVPKEY_WirelessDocking_AutoConnectDisallowed
0x18000e0b2  mov     [r9+164h], r8d
0x18000e0b9  mov     [r9+170h], edx
0x18000e0c0  movups  xmmword ptr [r9+1E0h], xmm0
0x18000e0c8  mov     [r9+1F0h], eax
0x18000e0cf  mov     eax, cs:DEVPKEY_NAME.pid
0x18000e0d5  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x18000e0dc  mov     [r9+174h], ebp
0x18000e0e3  mov     [r9+178h], rsi
0x18000e0ea  movups  xmmword ptr [r9+210h], xmm0
0x18000e0f2  mov     [r9+220h], eax
0x18000e0f9  mov     rax, r13
0x18000e0fc  mov     [r9+194h], r8d
0x18000e103  mov     [r9+1A0h], edx
0x18000e10a  mov     [r9+1A4h], ebp
0x18000e111  mov     [r9+1A8h], rsi
0x18000e118  mov     [r9+1C4h], r8d
0x18000e11f  mov     [r9+1D0h], edx
0x18000e126  mov     [r9+1D4h], ebp
0x18000e12d  mov     [r9+1D8h], rbx
0x18000e134  mov     [r9+1F4h], r8d
0x18000e13b  mov     [r9+200h], edx
0x18000e142  mov     [r9+204h], ebp
0x18000e149  mov     [r9+208h], rdi
0x18000e150  mov     [r9+224h], r8d
0x18000e157  mov     [r9+230h], r11d
0x18000e15e  inc     rax
0x18000e161  cmp     [r10+rax*2], r8w
0x18000e166  jnz     short loc_18000E15E
0x18000e168  lea     eax, ds:2[rax*2]
0x18000e16f  mov     [r9+238h], r10
0x18000e176  mov     [r9+234h], eax
0x18000e17d  mov     rax, [rsp+58h+arg_48]
0x18000e185  mov     dword ptr [rax], 0Ch
0x18000e18b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e192  lea     r15, WPP_GLOBAL_Control
0x18000e199  cmp     rcx, r15
0x18000e19c  jz      short loc_18000E1C2
0x18000e19e  cmp     byte ptr [rcx+19h], 3
0x18000e1a2  jb      short loc_18000E1C2
0x18000e1a4  test    [rcx+1Ch], bpl
0x18000e1a8  jz      short loc_18000E1C2
0x18000e1aa  mov     rcx, [rcx+10h]
0x18000e1ae  mov     edx, 2Dh ; '-'
0x18000e1b3  mov     r9, r10
0x18000e1b6  call    WPP_SF_S
0x18000e1bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1c2  lea     r12, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000e1c9  cmp     [rbx], r13b
0x18000e1cc  jnz     short loc_18000E1E6
0x18000e1ce  cmp     rcx, r15
0x18000e1d1  jz      short loc_18000E20F
0x18000e1d3  cmp     byte ptr [rcx+19h], 3
0x18000e1d7  jb      short loc_18000E20F
0x18000e1d9  test    [rcx+1Ch], bpl
0x18000e1dd  jz      short loc_18000E20F
0x18000e1df  mov     edx, 2Eh ; '.'
0x18000e1e4  jmp     short loc_18000E1FC
0x18000e1e6  cmp     rcx, r15
0x18000e1e9  jz      short loc_18000E20F
0x18000e1eb  cmp     byte ptr [rcx+19h], 3
0x18000e1ef  jb      short loc_18000E20F
0x18000e1f1  test    [rcx+1Ch], bpl
0x18000e1f5  jz      short loc_18000E20F
0x18000e1f7  mov     edx, 2Fh ; '/'
0x18000e1fc  mov     rcx, [rcx+10h]
0x18000e200  mov     r8, r12
0x18000e203  call    WPP_SF_
0x18000e208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e20f  cmp     [rdi], r13b
0x18000e212  jnz     short loc_18000E22C
0x18000e214  cmp     rcx, r15
0x18000e217  jz      short loc_18000E255
0x18000e219  cmp     byte ptr [rcx+19h], 3
0x18000e21d  jb      short loc_18000E255
0x18000e21f  test    [rcx+1Ch], bpl
0x18000e223  jz      short loc_18000E255
0x18000e225  mov     edx, 30h ; '0'
0x18000e22a  jmp     short loc_18000E242
0x18000e22c  cmp     rcx, r15
0x18000e22f  jz      short loc_18000E255
0x18000e231  cmp     byte ptr [rcx+19h], 3
0x18000e235  jb      short loc_18000E255
0x18000e237  test    [rcx+1Ch], bpl
0x18000e23b  jz      short loc_18000E255
0x18000e23d  mov     edx, 31h ; '1'
0x18000e242  mov     rcx, [rcx+10h]
0x18000e246  mov     r8, r12
0x18000e249  call    WPP_SF_
0x18000e24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e255  cmp     [rsi], r13b
0x18000e258  jnz     short loc_18000E272
0x18000e25a  cmp     rcx, r15
0x18000e25d  jz      short loc_18000E294
0x18000e25f  cmp     byte ptr [rcx+19h], 3
0x18000e263  jb      short loc_18000E294
0x18000e265  test    [rcx+1Ch], bpl
0x18000e269  jz      short loc_18000E294
0x18000e26b  mov     edx, 32h ; '2'
0x18000e270  jmp     short loc_18000E288
0x18000e272  cmp     rcx, r15
0x18000e275  jz      short loc_18000E294
0x18000e277  cmp     byte ptr [rcx+19h], 3
0x18000e27b  jb      short loc_18000E294
0x18000e27d  test    [rcx+1Ch], bpl
0x18000e281  jz      short loc_18000E294
0x18000e283  mov     edx, 33h ; '3'
0x18000e288  mov     rcx, [rcx+10h]
0x18000e28c  mov     r8, r12
0x18000e28f  call    WPP_SF_
0x18000e294  xor     eax, eax
0x18000e296  add     rsp, 20h
0x18000e29a  pop     r15
0x18000e29c  pop     r13
0x18000e29e  pop     r12
0x18000e2a0  pop     rdi
0x18000e2a1  pop     rsi
0x18000e2a2  pop     rbp
0x18000e2a3  pop     rbx
0x18000e2a4  retn
```
