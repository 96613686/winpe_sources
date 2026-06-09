# FveEasNetworkStatusImpl::GetCurrentStatus(Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> const &,FveEasNetworkStatusArgs &)

- ea: `0x180016628`
- end: `0x180016721`
- name: `?GetCurrentStatus@FveEasNetworkStatusImpl@@SAJAEBV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@AEAUFveEasNetworkStatusArgs@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64 *, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001472c`
- `0x1800180c0`
- `0x180025a18`

## callees

- `0x1800037a0`
- `0x180016628`
- `0x18001808c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall FveEasNetworkStatusImpl::GetCurrentStatus(__int64 *a1, bool *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  unsigned int v5; // eax
  int v6; // ebx
  unsigned int v7; // eax
  int v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  v9 = 0;
  *a2 = 0;
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a1 + 56LL);
  Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(&v10);
  v5 = v4(v3, &v10);
  v6 = v5;
  if ( !v5 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v5);
  if ( v6 >= 0 )
  {
LABEL_11:
    if ( v10 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, &v9);
      v6 = v7;
      if ( !v7 )
        goto LABEL_12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v7);
      if ( v6 >= 0 )
LABEL_12:
        *a2 = v9 == 3;
    }
  }
  Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016628  mov     rax, rsp
0x18001662b  mov     [rax+18h], rbx
0x18001662f  mov     [rax+20h], rsi
0x180016633  push    rdi
0x180016634  sub     rsp, 20h
0x180016638  mov     rsi, rdx
0x18001663b  mov     qword ptr [rax+10h], 0
0x180016643  mov     dword ptr [rax+8], 0
0x18001664a  mov     byte ptr [rdx], 0
0x18001664d  mov     rdi, [rcx]
0x180016650  mov     rax, [rdi]
0x180016653  mov     rbx, [rax+38h]
0x180016657  lea     rcx, [rsp+28h+arg_8]
0x18001665c  call    ?InternalRelease@?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(void)
0x180016661  lea     rdx, [rsp+28h+arg_8]
0x180016666  mov     rcx, rdi
0x180016669  mov     rax, rbx
0x18001666c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016671  mov     ebx, eax
0x180016673  lea     rdi, WPP_GLOBAL_Control
0x18001667a  test    eax, eax
0x18001667c  jz      short loc_1800166AC
0x18001667e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016685  cmp     rcx, rdi
0x180016688  jz      short loc_1800166A8
0x18001668a  test    byte ptr [rcx+1Ch], 40h
0x18001668e  jz      short loc_1800166A8
0x180016690  mov     edx, 95h
0x180016695  mov     r9d, eax
0x180016698  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18001669f  mov     rcx, [rcx+10h]
0x1800166a3  call    WPP_SF_d
0x1800166a8  test    ebx, ebx
0x1800166aa  js      short loc_180016705
0x1800166ac  mov     rcx, [rsp+28h+arg_8]
0x1800166b1  test    rcx, rcx
0x1800166b4  jz      short loc_180016705
0x1800166b6  mov     rax, [rcx]
0x1800166b9  lea     rdx, [rsp+28h+arg_0]
0x1800166be  mov     rax, [rax+38h]
0x1800166c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166c7  mov     ebx, eax
0x1800166c9  test    eax, eax
0x1800166cb  jz      short loc_1800166FB
0x1800166cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166d4  cmp     rcx, rdi
0x1800166d7  jz      short loc_1800166F7
0x1800166d9  test    byte ptr [rcx+1Ch], 40h
0x1800166dd  jz      short loc_1800166F7
0x1800166df  mov     edx, 96h
0x1800166e4  mov     r9d, eax
0x1800166e7  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800166ee  mov     rcx, [rcx+10h]
0x1800166f2  call    WPP_SF_d
0x1800166f7  test    ebx, ebx
0x1800166f9  js      short loc_180016705
0x1800166fb  cmp     [rsp+28h+arg_0], 3
0x180016700  setz    al
0x180016703  mov     [rsi], al
0x180016705  lea     rcx, [rsp+28h+arg_8]
0x18001670a  call    ?InternalRelease@?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(void)
0x18001670f  mov     eax, ebx
0x180016711  mov     rbx, [rsp+28h+arg_10]
0x180016716  mov     rsi, [rsp+28h+arg_18]
0x18001671b  add     rsp, 20h
0x18001671f  pop     rdi
0x180016720  retn
```
