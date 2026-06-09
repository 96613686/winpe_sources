# FindTriggersServiceName(void)

- ea: `0x180014054`
- end: `0x1800141c5`
- name: `?FindTriggersServiceName@@YA_NXZ`
- size: `369`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fcf0`

## callees

- `0x180004d88`
- `0x18000c654`
- `0x18000d87c`
- `0x180012c84`
- `0x180014054`
- `0x1800141cc`
- `0x180014634`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014116`
- `msvcrt!_wcsicmp` at `0x180014116`

## pseudocode

```c
char FindTriggersServiceName(void)
{
  int v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx

  if ( IsLocalSystemCluster() )
  {
    if ( !GetClusteredServiceName() )
      return 0;
    if ( _wcsicmp(&String1, L"MSMQTriggers") )
      v0 = StringCchPrintfW(
             &qword_18002D290,
             0x200u,
             L"%s%s%s",
             L"Software\\Microsoft\\MSMQ\\Triggers",
             L"\\Clustered\\",
             &String1);
    else
      v0 = StringCchCopyW(&qword_18002D290, 0x200u, L"Software\\Microsoft\\MSMQ\\Triggers");
    if ( v0 < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v2 = 28;
LABEL_10:
      WPP_SF_d(v1[2], v2, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids, (unsigned int)v0);
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  else
  {
    v0 = StringCchCopyW(&String1, 0xC8u, L"MSMQTriggers");
    if ( v0 < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v2 = 26;
      goto LABEL_10;
    }
    v0 = StringCchCopyW(&qword_18002D290, 0x200u, L"Software\\Microsoft\\MSMQ\\Triggers");
    if ( v0 < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v2 = 27;
      goto LABEL_10;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180014054  push    rbx
0x180014056  sub     rsp, 30h
0x18001405a  call    ?IsLocalSystemCluster@@YA_NXZ; IsLocalSystemCluster(void)
0x18001405f  test    al, al
0x180014061  jnz     loc_1800140FC
0x180014067  lea     r8, aMsmqtriggers; "MSMQTriggers"
0x18001406e  mov     edx, 0C8h; unsigned __int64
0x180014073  lea     rcx, String1; wchar_t *
0x18001407a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001407f  test    eax, eax
0x180014081  jns     short loc_1800140A3
0x180014083  mov     rcx, cs:WPP_GLOBAL_Control
0x18001408a  lea     rdx, WPP_GLOBAL_Control
0x180014091  cmp     rcx, rdx
0x180014094  jz      short loc_1800140F4
0x180014096  test    byte ptr [rcx+1Ch], 1
0x18001409a  jz      short loc_1800140F4
0x18001409c  mov     edx, 1Ah
0x1800140a1  jmp     short loc_1800140E1
0x1800140a3  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MSMQ\\Triggers"
0x1800140aa  mov     edx, 200h; unsigned __int64
0x1800140af  lea     rcx, qword_18002D290; wchar_t *
0x1800140b6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800140bb  test    eax, eax
0x1800140bd  jns     loc_1800141BE
0x1800140c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140ca  lea     rdx, WPP_GLOBAL_Control
0x1800140d1  cmp     rcx, rdx
0x1800140d4  jz      short loc_1800140F4
0x1800140d6  test    byte ptr [rcx+1Ch], 1
0x1800140da  jz      short loc_1800140F4
0x1800140dc  mov     edx, 1Bh
0x1800140e1  mov     rcx, [rcx+10h]
0x1800140e5  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x1800140ec  mov     r9d, eax
0x1800140ef  call    WPP_SF_d
0x1800140f4  xor     al, al
0x1800140f6  add     rsp, 30h
0x1800140fa  pop     rbx
0x1800140fb  retn
0x1800140fc  call    ?GetClusteredServiceName@@YA_NXZ; GetClusteredServiceName(void)
0x180014101  test    al, al
0x180014103  jz      short loc_1800140F4
0x180014105  lea     rbx, String1
0x18001410c  mov     rcx, rbx; String1
0x18001410f  lea     rdx, aMsmqtriggers; "MSMQTriggers"
0x180014116  call    cs:__imp__wcsicmp
0x18001411c  mov     edx, 200h; unsigned __int64
0x180014121  lea     rcx, qword_18002D290; wchar_t *
0x180014128  test    eax, eax
0x18001412a  jz      short loc_180014152
0x18001412c  lea     rax, aClustered; "\\Clustered\\"
0x180014133  mov     [rsp+38h+var_10], rbx
0x180014138  lea     r9, aSoftwareMicros; "Software\\Microsoft\\MSMQ\\Triggers"
0x18001413f  mov     [rsp+38h+var_18], rax
0x180014144  lea     r8, aSSS; "%s%s%s"
0x18001414b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180014150  jmp     short loc_18001415E
0x180014152  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MSMQ\\Triggers"
0x180014159  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001415e  test    eax, eax
0x180014160  jns     short loc_18001418D
0x180014162  mov     rcx, cs:WPP_GLOBAL_Control
0x180014169  lea     rdx, WPP_GLOBAL_Control
0x180014170  cmp     rcx, rdx
0x180014173  jz      loc_1800140F4
0x180014179  test    byte ptr [rcx+1Ch], 1
0x18001417d  jz      loc_1800140F4
0x180014183  mov     edx, 1Ch
0x180014188  jmp     loc_1800140E1
0x18001418d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014194  lea     rdx, WPP_GLOBAL_Control
0x18001419b  cmp     rcx, rdx
0x18001419e  jz      short loc_1800141BE
0x1800141a0  test    byte ptr [rcx+1Ch], 4
0x1800141a4  jz      short loc_1800141BE
0x1800141a6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800141aa  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x1800141b1  mov     edx, 1Dh
0x1800141b6  mov     r9, rbx
0x1800141b9  call    WPP_SF_S
0x1800141be  mov     al, 1
0x1800141c0  jmp     loc_1800140F6
```
