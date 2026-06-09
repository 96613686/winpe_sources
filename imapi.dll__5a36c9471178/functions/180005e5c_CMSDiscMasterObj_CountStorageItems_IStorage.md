# CMSDiscMasterObj::CountStorageItems(IStorage *)

- ea: `0x180005e5c`
- end: `0x180006202`
- name: `?CountStorageItems@CMSDiscMasterObj@@AEAAKPEAUIStorage@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *this, struct IStorage *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180004a40`
- `0x180005e5c`

## callees

- `0x180005e5c`
- `0x180007bac`
- `0x180007bd4`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000616e`
- `ole32!CoTaskMemFree` at `0x18000616e`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::CountStorageItems(CMSDiscMasterObj *this, struct IStorage *a2)
{
  unsigned int v4; // ebx
  _BYTE *v5; // rdi
  __int64 v6; // rcx
  int v7; // edi
  __int64 v9; // [rsp+40h] [rbp-49h] BYREF
  int v10; // [rsp+48h] [rbp-41h] BYREF
  struct IStorage *v11; // [rsp+50h] [rbp-39h] BYREF
  __int64 v12; // [rsp+58h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v14; // [rsp+68h] [rbp-21h]

  v9 = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
  v4 = 0;
  if ( a2
    && ((__int64 (__fastcall *)(struct IStorage *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IStorage,
         &v12) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
    if ( ((int (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, __int64 *))a2->lpVtbl->EnumElements)(
           a2,
           0,
           0,
           0,
           &v9) >= 0 )
    {
      v4 = 1;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, 1);
        v5 = WPP_GLOBAL_Control;
      }
      memset_0(&pv, 0, 0x50u);
      v6 = v9;
      v11 = 0;
      v10 = 0;
      if ( v9 )
      {
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9) >= 0 )
        {
          do
          {
            v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v9 + 24LL))(v9, 1, &pv, &v10);
            if ( v7 < 0 || !v10 )
              break;
            if ( v14 == 1 )
            {
              v7 = ((__int64 (__fastcall *)(struct IStorage *, LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, struct IStorage **))a2->lpVtbl->OpenStorage)(
                     a2,
                     pv,
                     0,
                     0,
                     0,
                     0,
                     &v11);
              if ( v7 >= 0
                || (v7 = ((__int64 (__fastcall *)(struct IStorage *, LPVOID, _QWORD, __int64, _QWORD, _DWORD, struct IStorage **))a2->lpVtbl->OpenStorage)(
                           a2,
                           pv,
                           0,
                           16,
                           0,
                           0,
                           &v11),
                    v7 >= 0) )
              {
                v4 += CMSDiscMasterObj::CountStorageItems(this, v11);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    50,
                    &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                    v4);
                }
                ((void (__fastcall *)(struct IStorage *))v11->lpVtbl->Release)(v11);
              }
            }
            else if ( v14 == 2 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v4);
              }
              ++v4;
            }
            else
            {
              if ( v14 - 3 < 2 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
                }
              }
              else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v14);
              }
              v7 = -2147024809;
            }
            if ( pv )
              CoTaskMemFree(pv);
          }
          while ( v7 >= 0 );
        }
      }
      else
      {
        if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || (v5[68] & 1) == 0 )
        {
LABEL_45:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v4);
          return v4;
        }
        WPP_SF_(*((_QWORD *)v5 + 7), 48, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
      }
      v6 = v9;
      goto LABEL_45;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180005e5c  mov     [rsp-8+arg_10], rbx
0x180005e61  mov     [rsp-8+arg_18], rsi
0x180005e66  push    rbp
0x180005e67  push    rdi
0x180005e68  push    r12
0x180005e6a  push    r13
0x180005e6c  push    r14
0x180005e6e  lea     rbp, [rsp-37h]
0x180005e73  sub     rsp, 0C0h
0x180005e7a  mov     rax, cs:__security_cookie
0x180005e81  xor     rax, rsp
0x180005e84  mov     [rbp+57h+var_30], rax
0x180005e88  mov     rsi, rdx
0x180005e8b  mov     [rbp+57h+var_A0], 0
0x180005e93  mov     r14, rcx
0x180005e96  mov     [rbp+57h+var_88], 0
0x180005e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ea5  lea     r13, WPP_GLOBAL_Control
0x180005eac  mov     r12d, 1
0x180005eb2  cmp     rcx, r13
0x180005eb5  jz      short loc_180005ED2
0x180005eb7  test    [rcx+44h], r12b
0x180005ebb  jz      short loc_180005ED2
0x180005ebd  mov     rcx, [rcx+38h]
0x180005ec1  lea     edx, [r12+2Ch]
0x180005ec6  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005ecd  call    WPP_SF_
0x180005ed2  xor     ebx, ebx
0x180005ed4  test    rsi, rsi
0x180005ed7  jz      loc_1800061D8
0x180005edd  mov     rax, [rsi]
0x180005ee0  lea     r8, [rbp+57h+var_88]
0x180005ee4  lea     rdx, IID_IStorage
0x180005eeb  mov     rcx, rsi
0x180005eee  mov     rax, [rax]
0x180005ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef6  test    eax, eax
0x180005ef8  js      loc_1800061D8
0x180005efe  mov     rcx, [rbp+57h+var_88]
0x180005f02  mov     rax, [rcx]
0x180005f05  mov     rax, [rax+10h]
0x180005f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f15  cmp     rcx, r13
0x180005f18  jz      short loc_180005F33
0x180005f1a  test    [rcx+44h], r12b
0x180005f1e  jz      short loc_180005F33
0x180005f20  mov     rcx, [rcx+38h]
0x180005f24  lea     edx, [rbx+2Eh]
0x180005f27  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005f2e  call    WPP_SF_
0x180005f33  mov     rax, [rsi]
0x180005f36  lea     rcx, [rbp+57h+var_A0]
0x180005f3a  mov     [rsp+0E0h+var_C0], rcx
0x180005f3f  xor     r9d, r9d
0x180005f42  xor     r8d, r8d
0x180005f45  xor     edx, edx
0x180005f47  mov     rcx, rsi
0x180005f4a  mov     rax, [rax+58h]
0x180005f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f53  test    eax, eax
0x180005f55  js      loc_1800061D8
0x180005f5b  mov     ebx, r12d
0x180005f5e  mov     rdi, cs:WPP_GLOBAL_Control
0x180005f65  cmp     rdi, r13
0x180005f68  jz      short loc_180005F8F
0x180005f6a  test    [rdi+44h], r12b
0x180005f6e  jz      short loc_180005F8F
0x180005f70  mov     rcx, [rdi+38h]
0x180005f74  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180005f7b  mov     edx, 2Fh ; '/'
0x180005f80  mov     r9d, r12d
0x180005f83  call    WPP_SF_d
0x180005f88  mov     rdi, cs:WPP_GLOBAL_Control
0x180005f8f  xor     edx, edx; Val
0x180005f91  lea     rcx, [rbp+57h+pv]; void *
0x180005f95  lea     r8d, [rdx+50h]; Size
0x180005f99  call    memset_0
0x180005f9e  mov     rcx, [rbp+57h+var_A0]
0x180005fa2  mov     [rbp+57h+var_90], 0
0x180005faa  mov     [rbp+57h+var_98], 0
0x180005fb1  test    rcx, rcx
0x180005fb4  jz      loc_18000617E
0x180005fba  mov     rax, [rcx]
0x180005fbd  mov     rax, [rax+28h]
0x180005fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc6  test    eax, eax
0x180005fc8  js      loc_18000619E
0x180005fce  mov     rcx, [rbp+57h+var_A0]
0x180005fd2  lea     r9, [rbp+57h+var_98]
0x180005fd6  lea     r8, [rbp+57h+pv]
0x180005fda  mov     edx, r12d
0x180005fdd  mov     rax, [rcx]
0x180005fe0  mov     rax, [rax+18h]
0x180005fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe9  mov     edi, eax
0x180005feb  test    eax, eax
0x180005fed  js      loc_18000619E
0x180005ff3  cmp     [rbp+57h+var_98], 0
0x180005ff7  jz      loc_18000619E
0x180005ffd  mov     r9d, [rbp+57h+var_78]
0x180006001  mov     ecx, r9d
0x180006004  sub     ecx, r12d
0x180006007  jz      loc_1800060A8
0x18000600d  sub     ecx, r12d
0x180006010  jz      short loc_180006076
0x180006012  sub     ecx, r12d
0x180006015  jz      short loc_180006045
0x180006017  cmp     ecx, r12d
0x18000601a  jz      short loc_180006045
0x18000601c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006023  cmp     rcx, r13
0x180006026  jz      short loc_18000606C
0x180006028  test    [rcx+44h], r12b
0x18000602c  jz      short loc_18000606C
0x18000602e  mov     rcx, [rcx+38h]
0x180006032  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006039  mov     edx, 34h ; '4'
0x18000603e  call    WPP_SF_d
0x180006043  jmp     short loc_18000606C
0x180006045  mov     rcx, cs:WPP_GLOBAL_Control
0x18000604c  cmp     rcx, r13
0x18000604f  jz      short loc_18000606C
0x180006051  test    [rcx+44h], r12b
0x180006055  jz      short loc_18000606C
0x180006057  mov     rcx, [rcx+38h]
0x18000605b  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006062  mov     edx, 31h ; '1'
0x180006067  call    WPP_SF_
0x18000606c  mov     edi, 80070057h
0x180006071  jmp     loc_180006165
0x180006076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000607d  cmp     rcx, r13
0x180006080  jz      short loc_1800060A0
0x180006082  test    [rcx+44h], r12b
0x180006086  jz      short loc_1800060A0
0x180006088  mov     rcx, [rcx+38h]
0x18000608c  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006093  mov     edx, 33h ; '3'
0x180006098  mov     r9d, ebx
0x18000609b  call    WPP_SF_d
0x1800060a0  add     ebx, r12d
0x1800060a3  jmp     loc_180006165
0x1800060a8  mov     rax, [rsi]
0x1800060ab  lea     rcx, [rbp+57h+var_90]
0x1800060af  mov     rdx, [rbp+57h+pv]
0x1800060b3  xor     r9d, r9d
0x1800060b6  mov     [rsp+0E0h+var_B0], rcx
0x1800060bb  xor     r8d, r8d
0x1800060be  mov     [rsp+0E0h+var_B8], 0
0x1800060c6  mov     rcx, rsi
0x1800060c9  mov     rax, [rax+30h]
0x1800060cd  mov     [rsp+0E0h+var_C0], 0
0x1800060d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060db  mov     edi, eax
0x1800060dd  test    eax, eax
0x1800060df  jns     short loc_18000611D
0x1800060e1  mov     rax, [rsi]
0x1800060e4  lea     rcx, [rbp+57h+var_90]
0x1800060e8  mov     rdx, [rbp+57h+pv]
0x1800060ec  mov     r9d, 10h
0x1800060f2  mov     [rsp+0E0h+var_B0], rcx
0x1800060f7  xor     r8d, r8d
0x1800060fa  mov     [rsp+0E0h+var_B8], 0
0x180006102  mov     rcx, rsi
0x180006105  mov     rax, [rax+30h]
0x180006109  mov     [rsp+0E0h+var_C0], 0
0x180006112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006117  mov     edi, eax
0x180006119  test    eax, eax
0x18000611b  js      short loc_180006165
0x18000611d  mov     rdx, [rbp+57h+var_90]; struct IStorage *
0x180006121  mov     rcx, r14; this
0x180006124  call    ?CountStorageItems@CMSDiscMasterObj@@AEAAKPEAUIStorage@@@Z; CMSDiscMasterObj::CountStorageItems(IStorage *)
0x180006129  add     ebx, eax
0x18000612b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006132  cmp     rcx, r13
0x180006135  jz      short loc_180006155
0x180006137  test    [rcx+44h], r12b
0x18000613b  jz      short loc_180006155
0x18000613d  mov     rcx, [rcx+38h]
0x180006141  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006148  mov     edx, 32h ; '2'
0x18000614d  mov     r9d, ebx
0x180006150  call    WPP_SF_d
0x180006155  mov     rcx, [rbp+57h+var_90]
0x180006159  mov     rax, [rcx]
0x18000615c  mov     rax, [rax+10h]
0x180006160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006165  mov     rcx, [rbp+57h+pv]; pv
0x180006169  test    rcx, rcx
0x18000616c  jz      short loc_180006174
0x18000616e  call    cs:__imp_CoTaskMemFree
0x180006174  test    edi, edi
0x180006176  jns     loc_180005FCE
0x18000617c  jmp     short loc_18000619E
0x18000617e  cmp     rdi, r13
0x180006181  jz      short loc_1800061A2
0x180006183  test    [rdi+44h], r12b
0x180006187  jz      short loc_1800061A2
0x180006189  mov     rcx, [rdi+38h]
0x18000618d  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180006194  mov     edx, 30h ; '0'
0x180006199  call    WPP_SF_
0x18000619e  mov     rcx, [rbp+57h+var_A0]
0x1800061a2  mov     rax, [rcx]
0x1800061a5  mov     rax, [rax+10h]
0x1800061a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061b5  cmp     rcx, r13
0x1800061b8  jz      short loc_1800061D8
0x1800061ba  test    [rcx+44h], r12b
0x1800061be  jz      short loc_1800061D8
0x1800061c0  mov     rcx, [rcx+38h]
0x1800061c4  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x1800061cb  mov     edx, 35h ; '5'
0x1800061d0  mov     r9d, ebx
0x1800061d3  call    WPP_SF_d
0x1800061d8  mov     eax, ebx
0x1800061da  mov     rcx, [rbp+57h+var_30]
0x1800061de  xor     rcx, rsp; StackCookie
0x1800061e1  call    __security_check_cookie
0x1800061e6  lea     r11, [rsp+0E0h+var_20]
0x1800061ee  mov     rbx, [r11+40h]
0x1800061f2  mov     rsi, [r11+48h]
0x1800061f6  mov     rsp, r11
0x1800061f9  pop     r14
0x1800061fb  pop     r13
0x1800061fd  pop     r12
0x1800061ff  pop     rdi
0x180006200  pop     rbp
0x180006201  retn
```
