# CProfileTask_OnDelete::Execute(void)

- ea: `0x180014c20`
- end: `0x180014ec4`
- name: `?Execute@CProfileTask_OnDelete@@UEAAJXZ`
- size: `676`
- prototype: `__int64 __fastcall(CProfileTask_OnDelete *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006c00`
- `0x18000b390`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014140`
- `0x180014718`
- `0x180014c20`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e2f`

## pseudocode

```c
__int64 __fastcall CProfileTask_OnDelete::Execute(CProfileTask_OnDelete *this)
{
  int v2; // ebx
  CProfileDeleteProgress *v3; // rax
  CProfileDeleteProgress *v4; // rax
  CProfileDeleteProgress *v5; // rdi
  __int64 v7; // [rsp+50h] [rbp-20h] BYREF
  __int64 v8; // [rsp+58h] [rbp-18h] BYREF
  __int64 v9; // [rsp+60h] [rbp-10h] BYREF
  LPVOID v10; // [rsp+68h] [rbp-8h] BYREF
  int v11; // [rsp+A0h] [rbp+30h] BYREF
  void *v12; // [rsp+A8h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+48h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200000) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids);
  v12 = 0;
  v2 = CInterfaceInGITBase::_Unmarshal(
         (CProfileTask_OnDelete *)((char *)this + 8),
         &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
         &v12);
  if ( v2 >= 0 )
  {
    v9 = 0;
    v2 = -2147024882;
    v3 = (CProfileDeleteProgress *)operator new(0x10u);
    if ( v3 )
    {
      v4 = CProfileDeleteProgress::CProfileDeleteProgress(v3);
      v5 = v4;
      if ( v4 )
      {
        v2 = (**(__int64 (__fastcall ***)(CProfileDeleteProgress *, GUID *, __int64 *))v4)(
               v4,
               &IID_IOfflineFilesSimpleProgress,
               &v9);
        (*(void (__fastcall **)(CProfileDeleteProgress *))(*(_QWORD *)v5 + 16LL))(v5);
        if ( v2 >= 0 )
        {
          v8 = 0;
          v2 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v12)(
                 v12,
                 &GUID_3836f049_9413_45dd_bf46_b5aaa82dc310,
                 &v8);
          if ( v2 >= 0 )
          {
            v7 = 0;
            v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, unsigned int, __int64 *))(*(_QWORD *)v8 + 32LL))(
                   v8,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0x80000000,
                   &v7);
            if ( v2 >= 0 )
            {
              v14 = 0;
              v11 = 0;
              while ( 1 )
              {
                v2 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v7 + 24LL))(
                       v7,
                       1,
                       &v14,
                       &v11);
                if ( v2 )
                  break;
                pv = 0;
                if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 32LL))(v14, &pv) >= 0 )
                {
                  v10 = pv;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200000) != 0 )
                  {
                    WPP_SF_SS(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      v2 + 22,
                      (unsigned int)WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids,
                      (_DWORD)pv,
                      *((_QWORD *)this + 12));
                  }
                  (*(void (__fastcall **)(void *, _QWORD, LPVOID *, __int64, int, _DWORD, __int64))(*(_QWORD *)v12 + 40LL))(
                    v12,
                    *((_QWORD *)this + 12),
                    &v10,
                    1,
                    -2147483644,
                    0,
                    v9);
                  CoTaskMemFree(pv);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200000) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      23,
      WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180014c20  push    rbp
0x180014c22  push    rbx
0x180014c23  push    rsi
0x180014c24  push    rdi
0x180014c25  push    r12
0x180014c27  mov     rbp, rsp
0x180014c2a  sub     rsp, 70h
0x180014c2e  mov     rsi, rcx
0x180014c31  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c38  lea     r12, WPP_GLOBAL_Control
0x180014c3f  cmp     rcx, r12
0x180014c42  jz      short loc_180014C62
0x180014c44  test    dword ptr [rcx+1Ch], 200000h
0x180014c4b  jz      short loc_180014C62
0x180014c4d  mov     rcx, [rcx+10h]
0x180014c51  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014c58  mov     edx, 15h
0x180014c5d  call    WPP_SF_
0x180014c62  lea     rcx, [rsi+8]; this
0x180014c66  mov     [rbp+arg_8], 0
0x180014c6e  lea     r8, [rbp+arg_8]; void **
0x180014c72  lea     rdx, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; struct _GUID *
0x180014c79  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x180014c7e  mov     ebx, eax
0x180014c80  test    eax, eax
0x180014c82  js      loc_180014E8A
0x180014c88  mov     ecx, 10h; Size
0x180014c8d  mov     [rbp+var_10], 0
0x180014c95  mov     ebx, 8007000Eh
0x180014c9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014c9f  test    rax, rax
0x180014ca2  jz      loc_180014E7A
0x180014ca8  mov     rcx, rax; this
0x180014cab  call    ??0CProfileDeleteProgress@@AEAA@XZ; CProfileDeleteProgress::CProfileDeleteProgress(void)
0x180014cb0  mov     rdi, rax
0x180014cb3  test    rax, rax
0x180014cb6  jz      loc_180014E7A
0x180014cbc  mov     rcx, [rax]
0x180014cbf  lea     r8, [rbp+var_10]
0x180014cc3  lea     rdx, IID_IOfflineFilesSimpleProgress
0x180014cca  mov     rax, [rcx]
0x180014ccd  mov     rcx, rdi
0x180014cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cd5  mov     rcx, [rdi]
0x180014cd8  mov     ebx, eax
0x180014cda  mov     rax, [rcx+10h]
0x180014cde  mov     rcx, rdi
0x180014ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ce6  test    ebx, ebx
0x180014ce8  js      loc_180014E7A
0x180014cee  mov     rcx, [rbp+arg_8]
0x180014cf2  lea     r8, [rbp+var_18]
0x180014cf6  mov     [rbp+var_18], 0
0x180014cfe  lea     rdx, _GUID_3836f049_9413_45dd_bf46_b5aaa82dc310
0x180014d05  mov     rax, [rcx]
0x180014d08  mov     rax, [rax]
0x180014d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d10  mov     ebx, eax
0x180014d12  test    eax, eax
0x180014d14  js      loc_180014E6A
0x180014d1a  mov     rcx, [rbp+var_18]
0x180014d1e  lea     rdx, [rbp+var_20]
0x180014d22  mov     [rsp+70h+var_38], rdx
0x180014d27  xor     r9d, r9d
0x180014d2a  mov     [rbp+var_20], 0
0x180014d32  xor     r8d, r8d
0x180014d35  mov     dword ptr [rsp+70h+var_40], 80000000h
0x180014d3d  xor     edx, edx
0x180014d3f  mov     rax, [rcx]
0x180014d42  mov     [rsp+70h+var_48], 0
0x180014d4a  mov     [rsp+70h+var_50], 0
0x180014d53  mov     rax, [rax+20h]
0x180014d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d5c  mov     ebx, eax
0x180014d5e  test    eax, eax
0x180014d60  js      loc_180014E5A
0x180014d66  mov     [rbp+arg_18], 0
0x180014d6e  mov     edi, 1
0x180014d73  mov     [rbp+arg_0], 0
0x180014d7a  mov     rcx, [rbp+var_20]
0x180014d7e  lea     r9, [rbp+arg_0]
0x180014d82  lea     r8, [rbp+arg_18]
0x180014d86  mov     edx, edi
0x180014d88  mov     rax, [rcx]
0x180014d8b  mov     rax, [rax+18h]
0x180014d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d94  mov     ebx, eax
0x180014d96  test    eax, eax
0x180014d98  jnz     loc_180014E4A
0x180014d9e  mov     rcx, [rbp+arg_18]
0x180014da2  lea     rdx, [rbp+pv]
0x180014da6  mov     [rbp+pv], 0
0x180014dae  mov     rax, [rcx]
0x180014db1  mov     rax, [rax+20h]
0x180014db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dba  test    eax, eax
0x180014dbc  js      short loc_180014E35
0x180014dbe  mov     r9, [rbp+pv]
0x180014dc2  mov     [rbp+var_8], r9
0x180014dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dcd  cmp     rcx, r12
0x180014dd0  jz      short loc_180014DF7
0x180014dd2  test    dword ptr [rcx+1Ch], 200000h
0x180014dd9  jz      short loc_180014DF7
0x180014ddb  mov     rax, [rsi+60h]
0x180014ddf  lea     edx, [rbx+16h]
0x180014de2  mov     rcx, [rcx+10h]
0x180014de6  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014ded  mov     [rsp+70h+var_50], rax
0x180014df2  call    WPP_SF_SS
0x180014df7  mov     rdx, [rbp+var_10]
0x180014dfb  lea     r8, [rbp+var_8]
0x180014dff  mov     rcx, [rbp+arg_8]
0x180014e03  mov     r9d, edi
0x180014e06  mov     [rsp+70h+var_40], rdx
0x180014e0b  mov     rdx, [rsi+60h]
0x180014e0f  mov     [rsp+70h+var_48], 0
0x180014e17  mov     rax, [rcx]
0x180014e1a  mov     dword ptr [rsp+70h+var_50], 80000004h
0x180014e22  mov     rax, [rax+28h]
0x180014e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e2b  mov     rcx, [rbp+pv]; pv
0x180014e2f  call    cs:__imp_CoTaskMemFree
0x180014e35  mov     rcx, [rbp+arg_18]
0x180014e39  mov     rax, [rcx]
0x180014e3c  mov     rax, [rax+10h]
0x180014e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e45  jmp     loc_180014D7A
0x180014e4a  mov     rcx, [rbp+var_20]
0x180014e4e  mov     rax, [rcx]
0x180014e51  mov     rax, [rax+10h]
0x180014e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e5a  mov     rcx, [rbp+var_18]
0x180014e5e  mov     rax, [rcx]
0x180014e61  mov     rax, [rax+10h]
0x180014e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e6a  mov     rcx, [rbp+var_10]
0x180014e6e  mov     rax, [rcx]
0x180014e71  mov     rax, [rax+10h]
0x180014e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e7a  mov     rcx, [rbp+arg_8]
0x180014e7e  mov     rax, [rcx]
0x180014e81  mov     rax, [rax+10h]
0x180014e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e91  cmp     rcx, r12
0x180014e94  jz      short loc_180014EB7
0x180014e96  test    dword ptr [rcx+1Ch], 200000h
0x180014e9d  jz      short loc_180014EB7
0x180014e9f  mov     rcx, [rcx+10h]
0x180014ea3  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014eaa  mov     edx, 17h
0x180014eaf  mov     r9d, ebx
0x180014eb2  call    WPP_SF_d
0x180014eb7  mov     eax, ebx
0x180014eb9  add     rsp, 70h
0x180014ebd  pop     r12
0x180014ebf  pop     rdi
0x180014ec0  pop     rsi
0x180014ec1  pop     rbx
0x180014ec2  pop     rbp
0x180014ec3  retn
```
