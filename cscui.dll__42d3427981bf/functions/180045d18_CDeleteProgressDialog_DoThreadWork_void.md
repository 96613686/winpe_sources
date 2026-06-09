# CDeleteProgressDialog::_DoThreadWork(void)

- ea: `0x180045d18`
- end: `0x180045fdc`
- name: `?_DoThreadWork@CDeleteProgressDialog@@AEAAJXZ`
- size: `708`
- prototype: `__int64 __fastcall(CDeleteProgressDialog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046440`

## callees

- `0x180010ff4`
- `0x18001101c`
- `0x1800322a8`
- `0x180045270`
- `0x180045d18`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045dc6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045dc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180045f7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180045f7c`
- `USER32!SendMessageW` at `0x180045f08`
- `USER32!SendMessageW` at `0x180045f41`
- `USER32!SendMessageW` at `0x180045f59`
- `USER32!SendMessageW` at `0x180045f6f`
- `USER32!SendMessageW` at `0x180045f08`
- `USER32!SendMessageW` at `0x180045f41`
- `USER32!SendMessageW` at `0x180045f59`
- `USER32!SendMessageW` at `0x180045f6f`

## pseudocode

```c
__int64 __fastcall CDeleteProgressDialog::_DoThreadWork(CDeleteProgressDialog *this)
{
  _QWORD *v1; // r14
  int Instance; // eax
  unsigned int v4; // ebx
  UstCommon::CImpersonator *v5; // rcx
  HRESULT v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // r8d
  int v9; // r9d
  int v10; // ebp
  unsigned int v11; // eax
  HWND v12; // rcx
  int ppv; // [rsp+20h] [rbp-48h]
  int (*v15)(struct tagMSG *); // [rsp+28h] [rbp-40h]
  int *v16; // [rsp+30h] [rbp-38h]
  LPVOID v17; // [rsp+70h] [rbp+8h] BYREF
  HANDLE pHandles; // [rsp+78h] [rbp+10h] BYREF

  v1 = (_QWORD *)((char *)this + 248);
  Instance = CDeleteProgress::CreateInstance(
               *((HWND *)this + 3),
               *((void **)this + 27),
               *((_DWORD *)this + 60),
               (struct CDeleteProgress **)this + 31);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    v17 = 0;
    v6 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 3u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, &v17);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD))(**((_QWORD **)this + 32) + 8LL))(
             *((_QWORD *)this + 32),
             v17,
             *v1);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
      if ( (v4 & 0x80000000) == 0 )
      {
        v10 = 0;
        pHandles = (HANDLE)*((_QWORD *)this + 27);
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_110f8852164937b701b00ed210f9da85_Traceguids);
        }
        while ( !v10 )
        {
          v11 = CscUtil_WaitAndProcessThreadMessages(&pHandles, v7, v8, v9, ppv, v15, v16);
          if ( v11 == -1 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_110f8852164937b701b00ed210f9da85_Traceguids);
            }
            v4 = -2147467259;
            break;
          }
          if ( !v11 )
          {
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_110f8852164937b701b00ed210f9da85_Traceguids);
            }
            v10 = 1;
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_110f8852164937b701b00ed210f9da85_Traceguids,
        (unsigned int)v6);
    }
    if ( !*((_DWORD *)this + 8) )
    {
      v12 = (HWND)*((_QWORD *)this + 3);
      if ( v12 )
      {
        SendMessageW(v12, 0x46Cu, 3u, *((unsigned __int16 *)this + 116));
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_110f8852164937b701b00ed210f9da85_Traceguids);
        }
        SendMessageW(*((HWND *)this + 3), 0x46Fu, 2u, 0);
        SendMessageW(*((HWND *)this + 3), 0x46Bu, 0, 0xFFFFFFFFLL);
        SendMessageW(*((HWND *)this + 3), 0x46Cu, 0, (LPARAM)&lParam);
        *((_DWORD *)this + 9) = 1;
        *((_DWORD *)this + 10) = GetTickCount();
      }
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 16LL))(*v1);
    *v1 = 0;
    goto LABEL_31;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      WPP_110f8852164937b701b00ed210f9da85_Traceguids,
      (unsigned int)Instance);
LABEL_31:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x2000000) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 35, WPP_110f8852164937b701b00ed210f9da85_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180045d18  mov     [rsp+arg_10], rbx
0x180045d1d  mov     [rsp+arg_18], rbp
0x180045d22  push    rsi
0x180045d23  push    rdi
0x180045d24  push    r12
0x180045d26  push    r13
0x180045d28  push    r14
0x180045d2a  sub     rsp, 40h
0x180045d2e  mov     r8d, [rcx+0F0h]; unsigned int
0x180045d35  lea     r14, [rcx+0F8h]
0x180045d3c  mov     rdx, [rcx+0D8h]; void *
0x180045d43  mov     rdi, rcx
0x180045d46  mov     rcx, [rcx+18h]; HWND
0x180045d4a  mov     r9, r14; struct CDeleteProgress **
0x180045d4d  call    ?CreateInstance@CDeleteProgress@@SAJPEAUHWND__@@PEAXIPEAPEAV1@@Z; CDeleteProgress::CreateInstance(HWND__ *,void *,uint,CDeleteProgress * *)
0x180045d52  lea     r12, WPP_110f8852164937b701b00ed210f9da85_Traceguids
0x180045d59  mov     ebx, eax
0x180045d5b  mov     r13d, 2000000h
0x180045d61  test    eax, eax
0x180045d63  jns     short loc_180045D9F
0x180045d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d6c  lea     rsi, WPP_GLOBAL_Control
0x180045d73  cmp     rcx, rsi
0x180045d76  jz      loc_180045FC1
0x180045d7c  test    byte ptr [rcx+1Ch], 2
0x180045d80  jz      loc_180045FA2
0x180045d86  mov     rcx, [rcx+10h]
0x180045d8a  mov     edx, 1Dh
0x180045d8f  mov     r9d, eax
0x180045d92  mov     r8, r12
0x180045d95  call    WPP_SF_d
0x180045d9a  jmp     loc_180045F9B
0x180045d9f  xor     edx, edx; pUnkOuter
0x180045da1  mov     [rsp+68h+arg_0], 0
0x180045daa  lea     rax, [rsp+68h+arg_0]
0x180045daf  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180045db6  mov     [rsp+68h+ppv], rax; int
0x180045dbb  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180045dc2  lea     r8d, [rdx+3]; dwClsContext
0x180045dc6  call    cs:__imp_CoCreateInstance
0x180045dcc  lea     rsi, WPP_GLOBAL_Control
0x180045dd3  mov     ebx, eax
0x180045dd5  test    eax, eax
0x180045dd7  jns     short loc_180045E0C
0x180045dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180045de0  cmp     rcx, rsi
0x180045de3  jz      loc_180045EDC
0x180045de9  test    byte ptr [rcx+1Ch], 2
0x180045ded  jz      loc_180045EDC
0x180045df3  mov     rcx, [rcx+10h]
0x180045df7  mov     edx, 1Eh
0x180045dfc  mov     r9d, eax
0x180045dff  mov     r8, r12
0x180045e02  call    WPP_SF_d
0x180045e07  jmp     loc_180045EDC
0x180045e0c  mov     rcx, [rdi+100h]
0x180045e13  mov     r8, [r14]
0x180045e16  mov     rdx, [rsp+68h+arg_0]
0x180045e1b  mov     rax, [rcx]
0x180045e1e  mov     rax, [rax+8]
0x180045e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e27  mov     rcx, [rsp+68h+arg_0]
0x180045e2c  mov     ebx, eax
0x180045e2e  mov     rax, [rcx]
0x180045e31  mov     rax, [rax+10h]
0x180045e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e3a  test    ebx, ebx
0x180045e3c  js      loc_180045EDC
0x180045e42  mov     rax, [rdi+0D8h]
0x180045e49  xor     ebp, ebp
0x180045e4b  mov     [rsp+68h+pHandles], rax
0x180045e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e57  cmp     rcx, rsi
0x180045e5a  jz      short loc_180045E71
0x180045e5c  test    [rcx+1Ch], r13d
0x180045e60  jz      short loc_180045E71
0x180045e62  mov     rcx, [rcx+10h]
0x180045e66  lea     edx, [rbp+1Fh]
0x180045e69  mov     r8, r12
0x180045e6c  call    WPP_SF_
0x180045e71  test    ebp, ebp
0x180045e73  jnz     short loc_180045EDC
0x180045e75  lea     rcx, [rsp+68h+pHandles]; pHandles
0x180045e7a  call    ?CscUtil_WaitAndProcessThreadMessages@@YAKPEAPEAXKKHHP6AHPEAUtagMSG@@@ZPEAH@Z; CscUtil_WaitAndProcessThreadMessages(void * *,ulong,ulong,int,int,int (*)(tagMSG *),int *)
0x180045e7f  mov     ecx, 0FFFFFFFFh
0x180045e84  cmp     eax, ecx
0x180045e86  jz      short loc_180045EB4
0x180045e88  test    eax, eax
0x180045e8a  jnz     short loc_180045E71
0x180045e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e93  cmp     rcx, rsi
0x180045e96  jz      short loc_180045EAD
0x180045e98  test    [rcx+1Ch], r13d
0x180045e9c  jz      short loc_180045EAD
0x180045e9e  mov     rcx, [rcx+10h]
0x180045ea2  lea     edx, [rbp+21h]
0x180045ea5  mov     r8, r12
0x180045ea8  call    WPP_SF_
0x180045ead  mov     ebp, 1
0x180045eb2  jmp     short loc_180045E71
0x180045eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ebb  cmp     rcx, rsi
0x180045ebe  jz      short loc_180045ED7
0x180045ec0  test    byte ptr [rcx+1Ch], 2
0x180045ec4  jz      short loc_180045ED7
0x180045ec6  mov     rcx, [rcx+10h]
0x180045eca  mov     edx, 20h ; ' '
0x180045ecf  mov     r8, r12
0x180045ed2  call    WPP_SF_
0x180045ed7  mov     ebx, 80004005h
0x180045edc  cmp     dword ptr [rdi+20h], 0
0x180045ee0  jnz     loc_180045F85
0x180045ee6  mov     rcx, [rdi+18h]; hWnd
0x180045eea  test    rcx, rcx
0x180045eed  jz      loc_180045F85
0x180045ef3  movzx   r9d, word ptr [rdi+0E8h]; lParam
0x180045efb  mov     ebp, 46Ch
0x180045f00  mov     edx, ebp; Msg
0x180045f02  mov     r8d, 3; wParam
0x180045f08  call    cs:__imp_SendMessageW
0x180045f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f15  cmp     rcx, rsi
0x180045f18  jz      short loc_180045F31
0x180045f1a  test    [rcx+1Ch], r13d
0x180045f1e  jz      short loc_180045F31
0x180045f20  mov     rcx, [rcx+10h]
0x180045f24  mov     edx, 22h ; '"'
0x180045f29  mov     r8, r12
0x180045f2c  call    WPP_SF_
0x180045f31  mov     rcx, [rdi+18h]; hWnd
0x180045f35  xor     r9d, r9d; lParam
0x180045f38  mov     edx, 46Fh; Msg
0x180045f3d  lea     r8d, [r9+2]; wParam
0x180045f41  call    cs:__imp_SendMessageW
0x180045f47  mov     rcx, [rdi+18h]; hWnd
0x180045f4b  mov     r9d, 0FFFFFFFFh; lParam
0x180045f51  xor     r8d, r8d; wParam
0x180045f54  mov     edx, 46Bh; Msg
0x180045f59  call    cs:__imp_SendMessageW
0x180045f5f  mov     rcx, [rdi+18h]; hWnd
0x180045f63  lea     r9, lParam; lParam
0x180045f6a  xor     r8d, r8d; wParam
0x180045f6d  mov     edx, ebp; Msg
0x180045f6f  call    cs:__imp_SendMessageW
0x180045f75  mov     dword ptr [rdi+24h], 1
0x180045f7c  call    cs:__imp_GetTickCount
0x180045f82  mov     [rdi+28h], eax
0x180045f85  mov     rcx, [r14]
0x180045f88  mov     rax, [rcx]
0x180045f8b  mov     rax, [rax+10h]
0x180045f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f94  mov     qword ptr [r14], 0
0x180045f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fa2  cmp     rcx, rsi
0x180045fa5  jz      short loc_180045FC1
0x180045fa7  test    [rcx+1Ch], r13d
0x180045fab  jz      short loc_180045FC1
0x180045fad  mov     rcx, [rcx+10h]
0x180045fb1  mov     edx, 23h ; '#'
0x180045fb6  mov     r9d, ebx
0x180045fb9  mov     r8, r12
0x180045fbc  call    WPP_SF_d
0x180045fc1  lea     r11, [rsp+68h+var_28]
0x180045fc6  mov     eax, ebx
0x180045fc8  mov     rbx, [r11+40h]
0x180045fcc  mov     rbp, [r11+48h]
0x180045fd0  mov     rsp, r11
0x180045fd3  pop     r14
0x180045fd5  pop     r13
0x180045fd7  pop     r12
0x180045fd9  pop     rdi
0x180045fda  pop     rsi
0x180045fdb  retn
```
