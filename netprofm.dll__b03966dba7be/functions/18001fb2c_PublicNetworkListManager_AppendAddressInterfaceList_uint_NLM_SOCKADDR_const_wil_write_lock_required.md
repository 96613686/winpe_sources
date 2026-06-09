# PublicNetworkListManager::AppendAddressInterfaceList(uint,NLM_SOCKADDR const *,wil::write_lock_required)

- ea: `0x18001fb2c`
- end: `0x18001fe0b`
- name: `?AppendAddressInterfaceList@PublicNetworkListManager@@AEAAJIPEBUNLM_SOCKADDR@@Uwrite_lock_required@wil@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800293f0`
- `0x1800299c0`

## callees

- `0x180006810`
- `0x1800068d0`
- `0x1800120d0`
- `0x180012f40`
- `0x18001e698`
- `0x18001ee0c`
- `0x18001fb2c`
- `0x180023150`
- `0x18002b0c4`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001fd09`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001fd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fdf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fdf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fbfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fbfb`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::AppendAddressInterfaceList(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // r14d
  _OWORD *v8; // r12
  char *v9; // rax
  char *v10; // rbx
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  int v14; // r12d
  _QWORD v15[2]; // [rsp+30h] [rbp-79h] BYREF
  _OWORD v16[6]; // [rsp+40h] [rbp-69h] BYREF
  struct _GUID v17; // [rsp+A0h] [rbp-9h] BYREF
  struct _FILETIME FileTime; // [rsp+B0h] [rbp+7h] BYREF
  SYSTEMTIME SystemTime; // [rsp+B8h] [rbp+Fh] BYREF

  if ( *(_DWORD *)(a1 + 608) + a2 <= 0xA )
  {
    FileTime = 0;
    SystemTime = 0;
    v7 = 0;
    *(_DWORD *)&SystemTime.wYear = 67436;
    SystemTime.wDay = 1;
    if ( a2 )
    {
      while ( 1 )
      {
        v8 = (_OWORD *)(a3 + ((unsigned __int64)v7 << 7));
        if ( *(_QWORD *)PublicNetworkListManager::FindAddressInListNoLock(a1, v16, v8) == *(_QWORD *)(a1 + 600) )
        {
          v9 = (char *)CoTaskMemAlloc(0x150u);
          v10 = v9;
          if ( !v9 )
            return 2147942414LL;
          memset_0(v9, 0, 0x150u);
          ADDRESS_INTERFACE_DATA::ADDRESS_INTERFACE_DATA((ADDRESS_INTERFACE_DATA *)v10);
          *((_OWORD *)v10 + 1) = *v8;
          *((_OWORD *)v10 + 2) = v8[1];
          *((_OWORD *)v10 + 3) = v8[2];
          *((_OWORD *)v10 + 4) = v8[3];
          *((_OWORD *)v10 + 5) = v8[4];
          *((_OWORD *)v10 + 6) = v8[5];
          *((_OWORD *)v10 + 7) = v8[6];
          *((_OWORD *)v10 + 8) = v8[7];
          *(struct _GUID *)v10 = *GetConnectionIdFromInterfaceByteBlob(&v17, 0x80u, (const unsigned __int8 *)v10 + 16);
          *((_DWORD *)v10 + 36) = 0;
          *(_OWORD *)(v10 + 148) = 0;
          *(_OWORD *)(v10 + 164) = 0;
          *((_DWORD *)v10 + 45) = 0;
          *((_DWORD *)v10 + 46) = -1;
          *((_DWORD *)v10 + 51) = -1;
          *((_QWORD *)v10 + 26) = 0;
          *(GUID *)(v10 + 188) = GUID_NULL;
          *((_DWORD *)v10 + 54) = -1;
          *((_DWORD *)v10 + 55) = -1;
          *((_DWORD *)v10 + 56) = -1;
          *(_QWORD *)(v10 + 228) = 0;
          *((_DWORD *)v10 + 59) = -1;
          *((_DWORD *)v10 + 60) = 0;
          if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
            *(struct _FILETIME *)(v10 + 228) = FileTime;
          *((_QWORD *)v10 + 41) = 0;
          memset(&v16[3], 0, 48);
          v11 = v16[3];
          *(_OWORD *)(v10 + 248) = 0;
          v15[0] = v10;
          v12 = v16[4];
          *(_OWORD *)(v10 + 264) = 0;
          v15[1] = a1;
          *(_OWORD *)(v10 + 280) = v11;
          v13 = v16[5];
          *(_OWORD *)(v10 + 296) = v12;
          *(_OWORD *)(v10 + 312) = v13;
          v14 = wil::ResultFromException__PublicNetworkListManager::SetDestinationAddresses_::_48_::_lambda_1___(v15);
          if ( v14 < 0 )
            break;
        }
        if ( ++v7 >= a2 )
          return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          217,
          &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
          (unsigned int)v14);
      CoTaskMemFree(v10);
      return (unsigned int)v14;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LLd(*((_QWORD *)WPP_GLOBAL_Control + 2));
    return 2147483659LL;
  }
}

```

## disassembly

```asm
0x18001fb2c  mov     [rsp-8+arg_8], rbx
0x18001fb31  push    rbp
0x18001fb32  push    rsi
0x18001fb33  push    rdi
0x18001fb34  push    r12
0x18001fb36  push    r13
0x18001fb38  push    r14
0x18001fb3a  push    r15
0x18001fb3c  lea     rbp, [rsp-27h]
0x18001fb41  sub     rsp, 0D0h
0x18001fb48  mov     rax, cs:__security_cookie
0x18001fb4f  xor     rax, rsp
0x18001fb52  mov     [rbp+57h+var_38], rax
0x18001fb56  mov     r9d, [rcx+260h]
0x18001fb5d  mov     r13, r8
0x18001fb60  mov     esi, edx
0x18001fb62  mov     r15, rcx
0x18001fb65  lea     eax, [r9+rdx]
0x18001fb69  cmp     eax, 0Ah
0x18001fb6c  jbe     short loc_18001FBA3
0x18001fb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb75  lea     rax, WPP_GLOBAL_Control
0x18001fb7c  cmp     rcx, rax
0x18001fb7f  jz      short loc_18001FB99
0x18001fb81  mov     edi, 1
0x18001fb86  test    [rcx+1Ch], dil
0x18001fb8a  jz      short loc_18001FB99
0x18001fb8c  mov     rcx, [rcx+10h]
0x18001fb90  mov     [rsp+100h+var_E0], edx
0x18001fb94  call    WPP_SF_LLd
0x18001fb99  mov     eax, 8000000Bh
0x18001fb9e  jmp     loc_18001FD9E
0x18001fba3  xorps   xmm0, xmm0
0x18001fba6  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18001fbae  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001fbb2  xor     r14d, r14d
0x18001fbb5  mov     dword ptr [rbp+57h+SystemTime.wYear], 1076Ch
0x18001fbbc  mov     edi, 1
0x18001fbc1  mov     [rbp+57h+SystemTime.wDay], di
0x18001fbc5  test    esi, esi
0x18001fbc7  jz      loc_18001FD9C
0x18001fbcd  mov     r12d, r14d
0x18001fbd0  lea     rdx, [rbp+57h+var_C0]
0x18001fbd4  shl     r12, 7
0x18001fbd8  mov     rcx, r15
0x18001fbdb  add     r12, r13
0x18001fbde  mov     r8, r12
0x18001fbe1  call    ?FindAddressInListNoLock@PublicNetworkListManager@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAUADDRESS_INTERFACE_DATA@@@std@@@std@@@std@@PEAUsockaddr_storage@@@Z; PublicNetworkListManager::FindAddressInListNoLock(sockaddr_storage *)
0x18001fbe6  mov     rcx, [r15+258h]
0x18001fbed  cmp     [rax], rcx
0x18001fbf0  jnz     loc_18001FD90
0x18001fbf6  mov     ecx, 150h; cb
0x18001fbfb  call    cs:__imp_CoTaskMemAlloc
0x18001fc01  mov     rbx, rax
0x18001fc04  test    rax, rax
0x18001fc07  jz      loc_18001FE04
0x18001fc0d  xor     edx, edx; Val
0x18001fc0f  mov     r8d, 150h; Size
0x18001fc15  mov     rcx, rax; void *
0x18001fc18  call    memset_0
0x18001fc1d  mov     rcx, rbx; this
0x18001fc20  call    ??0ADDRESS_INTERFACE_DATA@@QEAA@XZ; ADDRESS_INTERFACE_DATA::ADDRESS_INTERFACE_DATA(void)
0x18001fc25  movups  xmm0, xmmword ptr [r12]
0x18001fc2a  lea     r8, [rbx+10h]; unsigned __int8 *
0x18001fc2e  mov     edx, 80h; unsigned int
0x18001fc33  lea     rcx, [rbp+57h+var_60]; retstr
0x18001fc37  movups  xmmword ptr [r8], xmm0
0x18001fc3b  movups  xmm1, xmmword ptr [r12+10h]
0x18001fc41  movups  xmmword ptr [r8+10h], xmm1
0x18001fc46  movups  xmm0, xmmword ptr [r12+20h]
0x18001fc4c  movups  xmmword ptr [r8+20h], xmm0
0x18001fc51  movups  xmm1, xmmword ptr [r12+30h]
0x18001fc57  movups  xmmword ptr [r8+30h], xmm1
0x18001fc5c  movups  xmm0, xmmword ptr [r12+40h]
0x18001fc62  movups  xmmword ptr [r8+40h], xmm0
0x18001fc67  movups  xmm1, xmmword ptr [r12+50h]
0x18001fc6d  movups  xmmword ptr [r8+50h], xmm1
0x18001fc72  movups  xmm0, xmmword ptr [r12+60h]
0x18001fc78  movups  xmmword ptr [r8+60h], xmm0
0x18001fc7d  movups  xmm1, xmmword ptr [r12+70h]
0x18001fc83  movups  xmmword ptr [r8+70h], xmm1
0x18001fc88  call    ?GetConnectionIdFromInterfaceByteBlob@@YA?AU_GUID@@KPEBE@Z; GetConnectionIdFromInterfaceByteBlob(ulong,uchar const *)
0x18001fc8d  xor     r12d, r12d
0x18001fc90  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001fc94  xorps   xmm0, xmm0
0x18001fc97  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001fc9b  movups  xmm1, xmmword ptr [rax]
0x18001fc9e  or      eax, 0FFFFFFFFh
0x18001fca1  movdqu  xmmword ptr [rbx], xmm1
0x18001fca5  mov     [rbx+90h], r12d
0x18001fcac  movups  xmmword ptr [rbx+94h], xmm0
0x18001fcb3  movups  xmmword ptr [rbx+0A4h], xmm0
0x18001fcba  mov     [rbx+0B4h], r12d
0x18001fcc1  mov     [rbx+0B8h], eax
0x18001fcc7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001fcce  mov     [rbx+0CCh], eax
0x18001fcd4  mov     [rbx+0D0h], r12
0x18001fcdb  movdqu  xmmword ptr [rbx+0BCh], xmm0
0x18001fce3  mov     [rbx+0D8h], eax
0x18001fce9  mov     [rbx+0DCh], eax
0x18001fcef  mov     [rbx+0E0h], eax
0x18001fcf5  mov     [rbx+0E4h], r12
0x18001fcfc  mov     [rbx+0ECh], eax
0x18001fd02  mov     [rbx+0F0h], r12d
0x18001fd09  call    cs:__imp_SystemTimeToFileTime
0x18001fd0f  test    eax, eax
0x18001fd11  jz      short loc_18001FD25
0x18001fd13  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x18001fd16  mov     [rbx+0E8h], eax
0x18001fd1c  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x18001fd1f  mov     [rbx+0E4h], eax
0x18001fd25  mov     [rbx+148h], r12
0x18001fd2c  lea     rcx, [rbp+57h+var_D0]
0x18001fd30  xorps   xmm0, xmm0
0x18001fd33  mov     dword ptr [rbp+57h+var_90], r12d
0x18001fd37  movups  [rbp+57h+var_90+4], xmm0
0x18001fd3b  mov     [rbp+57h+var_6C], r12d
0x18001fd3f  movups  [rbp+57h+var_7C], xmm0
0x18001fd43  mov     [rbp+57h+var_68], r12
0x18001fd47  movaps  xmm0, [rbp+57h+var_90]
0x18001fd4b  xorps   xmm1, xmm1
0x18001fd4e  movups  xmmword ptr [rbx+0F8h], xmm1
0x18001fd55  mov     [rbp+57h+var_D0], rbx
0x18001fd59  movaps  xmm1, xmmword ptr [rbp-29h]
0x18001fd5d  xorps   xmm2, xmm2
0x18001fd60  movups  xmmword ptr [rbx+108h], xmm2
0x18001fd67  mov     [rbp+57h+var_C8], r15
0x18001fd6b  movups  xmmword ptr [rbx+118h], xmm0
0x18001fd72  movaps  xmm0, [rbp+57h+var_7C+0Ch]
0x18001fd76  movups  xmmword ptr [rbx+128h], xmm1
0x18001fd7d  movups  xmmword ptr [rbx+138h], xmm0
0x18001fd84  call    wil__ResultFromException__PublicNetworkListManager__SetDestinationAddresses____48____lambda_1___
0x18001fd89  mov     r12d, eax
0x18001fd8c  test    eax, eax
0x18001fd8e  js      short loc_18001FDC5
0x18001fd90  add     r14d, edi
0x18001fd93  cmp     r14d, esi
0x18001fd96  jb      loc_18001FBCD
0x18001fd9c  xor     eax, eax
0x18001fd9e  mov     rcx, [rbp+57h+var_38]
0x18001fda2  xor     rcx, rsp; StackCookie
0x18001fda5  call    __security_check_cookie
0x18001fdaa  mov     rbx, [rsp+100h+arg_8]
0x18001fdb2  add     rsp, 0D0h
0x18001fdb9  pop     r15
0x18001fdbb  pop     r14
0x18001fdbd  pop     r13
0x18001fdbf  pop     r12
0x18001fdc1  pop     rdi
0x18001fdc2  pop     rsi
0x18001fdc3  pop     rbp
0x18001fdc4  retn
0x18001fdc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdcc  lea     rax, WPP_GLOBAL_Control
0x18001fdd3  cmp     rcx, rax
0x18001fdd6  jz      short loc_18001FDF6
0x18001fdd8  test    [rcx+1Ch], dil
0x18001fddc  jz      short loc_18001FDF6
0x18001fdde  mov     rcx, [rcx+10h]
0x18001fde2  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18001fde9  mov     edx, 0D9h
0x18001fdee  mov     r9d, r12d
0x18001fdf1  call    WPP_SF_d
0x18001fdf6  mov     rcx, rbx; pv
0x18001fdf9  call    cs:__imp_CoTaskMemFree
0x18001fdff  mov     eax, r12d
0x18001fe02  jmp     short loc_18001FD9E
0x18001fe04  mov     eax, 8007000Eh
0x18001fe09  jmp     short loc_18001FD9E
```
