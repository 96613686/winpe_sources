# CFwProfileViewRead::GetIconForNetwork(INetworkPrivate *,HICON__ * *)

- ea: `0x180020aec`
- end: `0x180020c28`
- name: `?GetIconForNetwork@CFwProfileViewRead@@AEAAJPEAUINetworkPrivate@@PEAPEAUHICON__@@@Z`
- size: `316`
- prototype: `int(CFwProfileViewRead *__hidden this, struct INetworkPrivate *, HICON *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020598`

## callees

- `0x180009924`
- `0x18000994c`
- `0x1800208f8`
- `0x180020aec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020be8`
- `USER32!GetSystemMetrics` at `0x180020b59`
- `USER32!GetSystemMetrics` at `0x180020b59`

## pseudocode

```c
__int64 __fastcall CFwProfileViewRead::GetIconForNetwork(
        CFwProfileViewRead *this,
        struct INetworkPrivate *a2,
        HICON *a3)
{
  unsigned int HICONFromBits; // ebx
  CFwCplLua *v6; // rcx
  __int64 (__fastcall *v7)(struct INetworkPrivate *, __int64, int *, LPVOID *); // rbx
  unsigned int SystemMetrics; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  v13 = HIDWORD(this);
  HICONFromBits = 0;
  v12 = 0;
  pv = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  *a3 = 0;
  if ( a2 )
  {
    v7 = *(__int64 (__fastcall **)(struct INetworkPrivate *, __int64, int *, LPVOID *))(*(_QWORD *)a2 + 64LL);
    SystemMetrics = GetSystemMetrics(49);
    v9 = 16;
    if ( SystemMetrics > 0x10 )
    {
      v9 = 24;
      if ( SystemMetrics > 0x18 )
      {
        v9 = 48;
        if ( SystemMetrics <= 0x20 )
          v9 = 32;
      }
    }
    v10 = v7(a2, v9, &v12, &pv);
    HICONFromBits = v10;
    if ( v10 >= 0 )
    {
      HICONFromBits = GetHICONFromBits((unsigned __int8 *)pv, a3);
      goto LABEL_14;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids,
        (unsigned int)v10);
LABEL_14:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 23, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, HICONFromBits);
  return HICONFromBits;
}

```

## disassembly

```asm
0x180020aec  mov     rax, rsp
0x180020aef  mov     [rax+18h], rbx
0x180020af3  mov     [rax+8], rcx
0x180020af7  push    rsi
0x180020af8  push    rdi
0x180020af9  push    r14
0x180020afb  sub     rsp, 30h
0x180020aff  xor     ebx, ebx
0x180020b01  mov     rsi, r8
0x180020b04  mov     [rax+8], ebx
0x180020b07  mov     rdi, rdx
0x180020b0a  mov     [rax+10h], rbx
0x180020b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b15  lea     r14, WPP_GLOBAL_Control
0x180020b1c  cmp     rcx, r14
0x180020b1f  jz      short loc_180020B41
0x180020b21  test    byte ptr [rcx+1Ch], 8
0x180020b25  jz      short loc_180020B41
0x180020b27  mov     rcx, [rcx+10h]
0x180020b2b  lea     edx, [rbx+15h]
0x180020b2e  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020b35  call    WPP_SF_
0x180020b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b41  mov     [rsi], rbx
0x180020b44  test    rdi, rdi
0x180020b47  jz      loc_180020BDB
0x180020b4d  mov     rax, [rdi]
0x180020b50  mov     ecx, 31h ; '1'; nIndex
0x180020b55  mov     rbx, [rax+40h]
0x180020b59  call    cs:__imp_GetSystemMetrics
0x180020b5f  mov     edx, 10h
0x180020b64  cmp     eax, edx
0x180020b66  jbe     short loc_180020B7E
0x180020b68  mov     edx, 18h
0x180020b6d  cmp     eax, edx
0x180020b6f  jbe     short loc_180020B7E
0x180020b71  mov     edx, 30h ; '0'
0x180020b76  lea     ecx, [rdx-10h]
0x180020b79  cmp     eax, ecx
0x180020b7b  cmovbe  edx, ecx
0x180020b7e  lea     r9, [rsp+48h+pv]
0x180020b83  mov     rcx, rdi
0x180020b86  lea     r8, [rsp+48h+arg_0]
0x180020b8b  mov     rax, rbx
0x180020b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b93  mov     ebx, eax
0x180020b95  test    eax, eax
0x180020b97  jns     short loc_180020BC5
0x180020b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ba0  cmp     rcx, r14
0x180020ba3  jz      short loc_180020BDB
0x180020ba5  test    byte ptr [rcx+1Ch], 1
0x180020ba9  jz      short loc_180020BDB
0x180020bab  mov     rcx, [rcx+10h]
0x180020baf  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020bb6  mov     edx, 16h
0x180020bbb  mov     r9d, eax
0x180020bbe  call    WPP_SF_d
0x180020bc3  jmp     short loc_180020BD4
0x180020bc5  mov     rcx, [rsp+48h+pv]; unsigned __int8 *
0x180020bca  mov     rdx, rsi; HICON *
0x180020bcd  call    ?GetHICONFromBits@@YAJPEAEPEAPEAUHICON__@@@Z; GetHICONFromBits(uchar *,HICON__ * *)
0x180020bd2  mov     ebx, eax
0x180020bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bdb  mov     rax, [rsp+48h+pv]
0x180020be0  test    rax, rax
0x180020be3  jz      short loc_180020BF5
0x180020be5  mov     rcx, rax; pv
0x180020be8  call    cs:__imp_CoTaskMemFree
0x180020bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bf5  cmp     rcx, r14
0x180020bf8  jz      short loc_180020C18
0x180020bfa  test    byte ptr [rcx+1Ch], 8
0x180020bfe  jz      short loc_180020C18
0x180020c00  mov     rcx, [rcx+10h]
0x180020c04  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020c0b  mov     edx, 17h
0x180020c10  mov     r9d, ebx
0x180020c13  call    WPP_SF_d
0x180020c18  mov     eax, ebx
0x180020c1a  mov     rbx, [rsp+48h+arg_10]
0x180020c1f  add     rsp, 30h
0x180020c23  pop     r14
0x180020c25  pop     rdi
0x180020c26  pop     rsi
0x180020c27  retn
```
