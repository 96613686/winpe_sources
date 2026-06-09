# DeleteTransportFilter

- ea: `0x18001d89c`
- end: `0x18001da53`
- name: `DeleteTransportFilter`
- size: `439`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x1800115f0`
- `0x180016120`
- `0x180029cac`
- `0x180029e00`

## callees

- `0x18000e510`
- `0x1800175dc`
- `0x18001cc18`
- `0x18001cc50`
- `0x18001d760`
- `0x18001d89c`
- `0x18001e950`
- `0x180044b5c`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d8d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d8d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d94f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d98d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d9fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d94f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d98d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d9fb`

## pseudocode

```c
__int64 __fastcall DeleteTransportFilter(__int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rcx
  unsigned int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF

  if ( !a1 )
    return 87;
  v10 = *(_OWORD *)(a1 + 16);
  EnterCriticalSection(&gcSPDSection);
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v5 = *(_DWORD *)(v2 + 156);
    if ( v5 <= 1 )
    {
      v7 = LipsApiIpsecFilterDelete(*(_QWORD *)(a1 + 8));
      if ( v7
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_d3e4a8f1960430b115941304a22a5749_Traceguids,
          &v10,
          v7);
      }
      v8 = DeleteIniTxFilter((_QWORD *)v2);
      RemoveTxFilterHandle(a1);
      SPDApiBufferFree(v9);
      LeaveCriticalSection(&gcSPDSection);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, &v10);
      return v8;
    }
    else
    {
      *(_DWORD *)(v2 + 164) = 1;
      *(_DWORD *)(v2 + 156) = v5 - 1;
      RemoveTxFilterHandle(a1);
      SPDApiBufferFree(v6);
      LeaveCriticalSection(&gcSPDSection);
      return 0;
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, 87);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
        WPP_SF__guid_D(v3[2], 57, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, &v10, 87);
    }
    LeaveCriticalSection(&gcSPDSection);
    return 87;
  }
}

```

## disassembly

```asm
0x18001d89c  mov     [rsp+arg_8], rbx
0x18001d8a1  mov     [rsp+arg_10], rsi
0x18001d8a6  push    rdi
0x18001d8a7  sub     rsp, 50h
0x18001d8ab  mov     rax, cs:__security_cookie
0x18001d8b2  xor     rax, rsp
0x18001d8b5  mov     [rsp+58h+var_18], rax
0x18001d8ba  mov     rbx, rcx
0x18001d8bd  test    rcx, rcx
0x18001d8c0  jz      loc_18001DA31
0x18001d8c6  movups  xmm0, xmmword ptr [rcx+10h]
0x18001d8ca  lea     rcx, gcSPDSection; lpCriticalSection
0x18001d8d1  movdqu  [rsp+58h+var_28], xmm0
0x18001d8d7  call    cs:__imp_EnterCriticalSection
0x18001d8dd  mov     rdi, [rbx+8]
0x18001d8e1  test    rdi, rdi
0x18001d8e4  jnz     short loc_18001D95C
0x18001d8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8ed  lea     rsi, WPP_GLOBAL_Control
0x18001d8f4  lea     ebx, [rdi+57h]
0x18001d8f7  cmp     rcx, rsi
0x18001d8fa  jz      short loc_18001D948
0x18001d8fc  test    byte ptr [rcx+1Ch], 10h
0x18001d900  jz      short loc_18001D91F
0x18001d902  mov     rcx, [rcx+10h]
0x18001d906  lea     edx, [rdi+36h]
0x18001d909  mov     r9d, ebx
0x18001d90c  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001d913  call    WPP_SF_d
0x18001d918  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d91f  cmp     rcx, rsi
0x18001d922  jz      short loc_18001D948
0x18001d924  test    byte ptr [rcx+1Ch], 10h
0x18001d928  jz      short loc_18001D948
0x18001d92a  mov     rcx, [rcx+10h]
0x18001d92e  lea     r9, [rsp+58h+var_28]
0x18001d933  mov     edx, 39h ; '9'
0x18001d938  mov     [rsp+58h+var_38], ebx
0x18001d93c  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001d943  call    WPP_SF__guid_D
0x18001d948  lea     rcx, gcSPDSection; lpCriticalSection
0x18001d94f  call    cs:__imp_LeaveCriticalSection
0x18001d955  mov     eax, ebx
0x18001d957  jmp     loc_18001DA36
0x18001d95c  mov     eax, [rdi+9Ch]
0x18001d962  cmp     eax, 1
0x18001d965  jbe     short loc_18001D99A
0x18001d967  dec     eax
0x18001d969  mov     dword ptr [rdi+0A4h], 1
0x18001d973  mov     rcx, rbx
0x18001d976  mov     [rdi+9Ch], eax
0x18001d97c  call    RemoveTxFilterHandle
0x18001d981  call    SPDApiBufferFree
0x18001d986  lea     rcx, gcSPDSection; lpCriticalSection
0x18001d98d  call    cs:__imp_LeaveCriticalSection
0x18001d993  xor     eax, eax
0x18001d995  jmp     loc_18001DA36
0x18001d99a  mov     rcx, rdi
0x18001d99d  call    LipsApiIpsecFilterDelete
0x18001d9a2  lea     rsi, WPP_GLOBAL_Control
0x18001d9a9  test    eax, eax
0x18001d9ab  jz      short loc_18001D9DD
0x18001d9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9b4  cmp     rcx, rsi
0x18001d9b7  jz      short loc_18001D9DD
0x18001d9b9  test    byte ptr [rcx+1Ch], 10h
0x18001d9bd  jz      short loc_18001D9DD
0x18001d9bf  mov     rcx, [rcx+10h]
0x18001d9c3  lea     r9, [rsp+58h+var_28]
0x18001d9c8  mov     edx, 37h ; '7'
0x18001d9cd  mov     [rsp+58h+var_38], eax
0x18001d9d1  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001d9d8  call    WPP_SF__guid_D
0x18001d9dd  mov     rcx, rdi; lpMem
0x18001d9e0  call    DeleteIniTxFilter
0x18001d9e5  mov     rcx, rbx
0x18001d9e8  mov     edi, eax
0x18001d9ea  call    RemoveTxFilterHandle
0x18001d9ef  call    SPDApiBufferFree
0x18001d9f4  lea     rcx, gcSPDSection; lpCriticalSection
0x18001d9fb  call    cs:__imp_LeaveCriticalSection
0x18001da01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da08  cmp     rcx, rsi
0x18001da0b  jz      short loc_18001DA2D
0x18001da0d  test    byte ptr [rcx+1Ch], 4
0x18001da11  jz      short loc_18001DA2D
0x18001da13  mov     rcx, [rcx+10h]
0x18001da17  lea     r9, [rsp+58h+var_28]
0x18001da1c  mov     edx, 38h ; '8'
0x18001da21  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001da28  call    WPP_SF__guid_
0x18001da2d  mov     eax, edi
0x18001da2f  jmp     short loc_18001DA36
0x18001da31  mov     eax, 57h ; 'W'
0x18001da36  mov     rcx, [rsp+58h+var_18]
0x18001da3b  xor     rcx, rsp; StackCookie
0x18001da3e  call    __security_check_cookie
0x18001da43  mov     rbx, [rsp+58h+arg_8]
0x18001da48  mov     rsi, [rsp+58h+arg_10]
0x18001da4d  add     rsp, 50h
0x18001da51  pop     rdi
0x18001da52  retn
```
