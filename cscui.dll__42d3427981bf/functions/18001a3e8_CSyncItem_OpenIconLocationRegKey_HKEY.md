# CSyncItem::_OpenIconLocationRegKey(HKEY__ * *)

- ea: `0x18001a3e8`
- end: `0x18001a5c7`
- name: `?_OpenIconLocationRegKey@CSyncItem@@AEAAJPEAPEAUHKEY__@@@Z`
- size: `479`
- prototype: `int(CSyncItem *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a6c0`

## callees

- `0x180003c20`
- `0x1800064d0`
- `0x180013dfc`
- `0x18001a3e8`
- `0x180032204`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a5a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a541`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a541`

## pseudocode

```c
__int64 __fastcall CSyncItem::_OpenIconLocationRegKey(CSyncItem *this, HKEY *a2)
{
  signed int HandlerIDString; // ebx
  __int64 v5; // rcx
  LSTATUS Key; // eax
  void *v7; // rdx
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v11[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+70h] [rbp-90h]
  __int128 v13; // [rsp+80h] [rbp-80h]
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h]
  __int128 v16; // [rsp+B0h] [rbp-50h]
  __int128 v17; // [rsp+C0h] [rbp-40h]
  __int128 v18; // [rsp+D0h] [rbp-30h]
  __int128 v19; // [rsp+E0h] [rbp-20h]
  __int128 v20; // [rsp+F0h] [rbp-10h]
  _OWORD v21[2]; // [rsp+100h] [rbp+0h]
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF

  *a2 = 0;
  HandlerIDString = SyncHandler_GetHandlerIDString(sz, 0x27u);
  if ( HandlerIDString >= 0 )
  {
    v5 = *((_QWORD *)this + 2);
    pv = 0;
    HandlerIDString = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v5 + 24LL))(v5, &pv);
    if ( HandlerIDString >= 0 )
    {
      v12 = *(_OWORD *)L"\\Microsoft\\Windows\\CurrentVersion\\SyncMgr\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      lpSubKey = 0;
      *(_OWORD *)v11 = *(_OWORD *)L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr\\HandlerInstances\\%1\\SyncItems"
                                   "\\%2\\DefaultIcon";
      v14 = *(_OWORD *)L"ws\\CurrentVersion\\SyncMgr\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v13 = *(_OWORD *)L"ft\\Windows\\CurrentVersion\\SyncMgr\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v16 = *(_OWORD *)L"n\\SyncMgr\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v15 = *(_OWORD *)L"ntVersion\\SyncMgr\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v18 = *(_OWORD *)L"rInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v17 = *(_OWORD *)L"r\\HandlerInstances\\%1\\SyncItems\\%2\\DefaultIcon";
      v20 = *(_OWORD *)L"ncItems\\%2\\DefaultIcon";
      v19 = *(_OWORD *)L"es\\%1\\SyncItems\\%2\\DefaultIcon";
      v21[0] = *(_OWORD *)L"%2\\DefaultIcon";
      *(_OWORD *)((char *)v21 + 14) = *(_OWORD *)L"ultIcon";
      HandlerIDString = CscUtil_FormatString((unsigned __int16 **)&lpSubKey, v11, sz, pv);
      if ( HandlerIDString >= 0 )
      {
        Key = RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0, 0, 0x20006u, 0, a2, 0);
        if ( Key )
        {
          if ( Key > 0 )
            HandlerIDString = (unsigned __int16)Key | 0x80070000;
          else
            HandlerIDString = Key;
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              71,
              (unsigned int)WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
              (_DWORD)lpSubKey,
              HandlerIDString);
          }
        }
        CscUtil_HeapFree((void *)lpSubKey, v7);
      }
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)HandlerIDString;
}

```

## disassembly

```asm
0x18001a3e8  mov     [rsp-8+arg_10], rbx
0x18001a3ed  push    rbp
0x18001a3ee  push    rsi
0x18001a3ef  push    rdi
0x18001a3f0  lea     rbp, [rsp-80h]
0x18001a3f5  sub     rsp, 180h
0x18001a3fc  mov     rax, cs:__security_cookie
0x18001a403  xor     rax, rsp
0x18001a406  mov     [rbp+90h+var_20], rax
0x18001a40a  mov     rdi, rdx
0x18001a40d  mov     qword ptr [rdx], 0
0x18001a414  mov     rsi, rcx
0x18001a417  mov     edx, 27h ; '''; cchMax
0x18001a41c  lea     rcx, [rbp+90h+sz]; lpsz
0x18001a420  call    ?SyncHandler_GetHandlerIDString@@YAJPEAG_K@Z; SyncHandler_GetHandlerIDString(ushort *,unsigned __int64)
0x18001a425  mov     ebx, eax
0x18001a427  test    eax, eax
0x18001a429  js      loc_18001A5A6
0x18001a42f  mov     rcx, [rsi+10h]
0x18001a433  lea     rdx, [rsp+190h+pv]
0x18001a438  mov     [rsp+190h+pv], 0
0x18001a441  mov     rax, [rcx]
0x18001a444  mov     rax, [rax+18h]
0x18001a448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a44d  mov     ebx, eax
0x18001a44f  test    eax, eax
0x18001a451  js      loc_18001A5A6
0x18001a457  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+10h; "\\Microsoft\\Windows\\CurrentVersion\\S"...
0x18001a45e  lea     r8, [rbp+90h+sz]
0x18001a462  movaps  xmm0, xmmword ptr cs:aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001a469  lea     rdx, [rsp+190h+var_130]; unsigned __int16 *
0x18001a46e  mov     r9, [rsp+190h+pv]
0x18001a473  lea     rcx, [rsp+190h+lpSubKey]; unsigned __int16 **
0x18001a478  movups  [rsp+190h+var_120], xmm1
0x18001a47d  mov     [rsp+190h+lpSubKey], 0
0x18001a486  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+30h; "ws\\CurrentVersion\\SyncMgr\\HandlerIns"...
0x18001a48d  movups  xmmword ptr [rsp+190h+var_130], xmm0
0x18001a492  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+20h; "ft\\Windows\\CurrentVersion\\SyncMgr\\H"...
0x18001a499  movups  [rbp+90h+var_100], xmm1
0x18001a49d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+50h; "n\\SyncMgr\\HandlerInstances\\%1\\SyncI"...
0x18001a4a4  movups  [rbp+90h+var_110], xmm0
0x18001a4a8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+40h; "ntVersion\\SyncMgr\\HandlerInstances\\%"...
0x18001a4af  movups  [rbp+90h+var_E0], xmm1
0x18001a4b3  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+70h; "rInstances\\%1\\SyncItems\\%2\\DefaultI"...
0x18001a4ba  movups  [rbp+90h+var_F0], xmm0
0x18001a4be  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+60h; "r\\HandlerInstances\\%1\\SyncItems\\%2"...
0x18001a4c5  movups  [rbp+90h+var_C0], xmm1
0x18001a4c9  movaps  xmm1, xmmword ptr cs:aSoftwareMicros+90h; "ncItems\\%2\\DefaultIcon"
0x18001a4d0  movups  [rbp+90h+var_D0], xmm0
0x18001a4d4  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+80h; "es\\%1\\SyncItems\\%2\\DefaultIcon"
0x18001a4db  movups  [rbp+90h+var_A0], xmm1
0x18001a4df  movups  xmm1, xmmword ptr cs:aSoftwareMicros+0AEh; "ultIcon"
0x18001a4e6  movups  [rbp+90h+var_B0], xmm0
0x18001a4ea  movaps  xmm0, xmmword ptr cs:aSoftwareMicros+0A0h; "%2\\DefaultIcon"
0x18001a4f1  movups  xmmword ptr [rbp+90h+var_90], xmm0
0x18001a4f5  movups  xmmword ptr [rbp+90h+var_90+0Eh], xmm1
0x18001a4f9  call    ?CscUtil_FormatString@@YAJPEAPEAGPEBGZZ; CscUtil_FormatString(ushort * *,ushort const *,...)
0x18001a4fe  mov     ebx, eax
0x18001a500  test    eax, eax
0x18001a502  js      loc_18001A59B
0x18001a508  mov     rdx, [rsp+190h+lpSubKey]; lpSubKey
0x18001a50d  xor     r9d, r9d; lpClass
0x18001a510  mov     [rsp+190h+lpdwDisposition], 0; lpdwDisposition
0x18001a519  xor     r8d, r8d; Reserved
0x18001a51c  mov     [rsp+190h+phkResult], rdi; phkResult
0x18001a521  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a528  mov     [rsp+190h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001a531  mov     [rsp+190h+samDesired], 20006h; samDesired
0x18001a539  mov     [rsp+190h+dwOptions], 0; dwOptions
0x18001a541  call    cs:__imp_RegCreateKeyExW
0x18001a547  test    eax, eax
0x18001a549  jz      short loc_18001A591
0x18001a54b  jg      short loc_18001A551
0x18001a54d  mov     ebx, eax
0x18001a54f  jmp     short loc_18001A55A
0x18001a551  movzx   ebx, ax
0x18001a554  or      ebx, 80070000h
0x18001a55a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a561  lea     rax, WPP_GLOBAL_Control
0x18001a568  cmp     rcx, rax
0x18001a56b  jz      short loc_18001A591
0x18001a56d  test    byte ptr [rcx+1Ch], 2
0x18001a571  jz      short loc_18001A591
0x18001a573  mov     r9, [rsp+190h+lpSubKey]
0x18001a578  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x18001a57f  mov     rcx, [rcx+10h]
0x18001a583  mov     edx, 47h ; 'G'
0x18001a588  mov     [rsp+190h+dwOptions], ebx
0x18001a58c  call    WPP_SF_Sd
0x18001a591  mov     rcx, [rsp+190h+lpSubKey]; lpMem
0x18001a596  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001a59b  mov     rcx, [rsp+190h+pv]; pv
0x18001a5a0  call    cs:__imp_CoTaskMemFree
0x18001a5a6  mov     eax, ebx
0x18001a5a8  mov     rcx, [rbp+90h+var_20]
0x18001a5ac  xor     rcx, rsp; StackCookie
0x18001a5af  call    __security_check_cookie
0x18001a5b4  mov     rbx, [rsp+190h+arg_10]
0x18001a5bc  add     rsp, 180h
0x18001a5c3  pop     rdi
0x18001a5c4  pop     rsi
0x18001a5c5  pop     rbp
0x18001a5c6  retn
```
