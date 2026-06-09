# BITSGetVolumeNameForVolumeMountPoint(ushort const *)

- ea: `0x180014004`
- end: `0x1800141c3`
- name: `?BITSGetVolumeNameForVolumeMountPoint@@YA?AV?$GenericStringHandle@G@@PEBG@Z`
- size: `447`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001c9c4`
- `0x180028d60`
- `0x180096bc4`
- `0x1800ee540`

## callees

- `0x180006640`
- `0x18000db20`
- `0x180014004`
- `0x180014310`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001419d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001419d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001404b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001410c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001404b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001410c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014037`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014037`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180014102`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180014102`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall BITSGetVolumeNameForVolumeMountPoint(void **a1, const WCHAR *a2)
{
  unsigned int LastError; // eax
  LPVOID v5; // r14
  __int64 v6; // rdi
  signed int v7; // ebx
  _QWORD *v8; // rax
  void **pExceptionObject; // [rsp+30h] [rbp-39h] BYREF
  __int128 v11; // [rsp+38h] [rbp-31h]
  unsigned int v12; // [rsp+48h] [rbp-21h]
  int v13; // [rsp+4Ch] [rbp-1Dh]
  int v14; // [rsp+50h] [rbp-19h]
  HANDLE *v15; // [rsp+E8h] [rbp+7Fh] BYREF

  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v15);
  if ( !RevertToSelf() )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v11 = 0;
    pExceptionObject = &ComError::`vftable';
    v12 = LastError;
    v13 = 227;
    v14 = 1;
    throw (ComError *)&pExceptionObject;
  }
  _InterlockedIncrement(&dword_180145058);
  *a1 = &GenericStringHandle<unsigned short>::s_EmptyString;
  v5 = operator new(0x76u);
  *(_QWORD *)v5 = 51;
  *((_DWORD *)v5 + 2) = 1;
  *((_WORD *)v5 + 6) = 0;
  v6 = -1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a1 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a1, 0x10u);
    *a1 = 0;
  }
  *a1 = v5;
  if ( !GetVolumeNameForVolumeMountPointW(a2, (LPWSTR)v5 + 6, 0x32u) )
  {
    v7 = GetLastError();
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        (unsigned int)v7);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v11 = 0;
    pExceptionObject = &ComError::`vftable';
    v12 = v7;
    v13 = 0;
    v14 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v8 = *a1;
  do
    ++v6;
  while ( *((_WORD *)v8 + v6 + 6) );
  *v8 = v6;
  SetThreadToken(0, *v15);
  TokenHandle::Decrement((TokenHandle *)&v15);
  return a1;
}

```

## disassembly

```asm
0x180014004  mov     [rsp-8+arg_0], rcx
0x180014009  push    rbp
0x18001400a  push    rbx
0x18001400b  push    rdi
0x18001400c  push    r12
0x18001400e  push    r13
0x180014010  push    r14
0x180014012  push    r15
0x180014014  lea     rbp, [rsp-27h]
0x180014019  sub     rsp, 90h
0x180014020  mov     r12, rdx
0x180014023  mov     rbx, rcx
0x180014026  xor     r13d, r13d
0x180014029  mov     [rbp+57h+var_A0], r13d
0x18001402d  lea     rcx, [rbp+57h+arg_18]; this
0x180014031  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x180014036  nop
0x180014037  call    cs:__imp_RevertToSelf
0x18001403d  test    eax, eax
0x18001403f  jnz     short loc_180014095
0x180014041  call    cs:__imp_GetLastError
0x180014047  test    eax, eax
0x180014049  jg      short loc_180014053
0x18001404b  call    cs:__imp_GetLastError
0x180014051  jmp     short loc_180014061
0x180014053  call    cs:__imp_GetLastError
0x180014059  movzx   eax, ax
0x18001405c  or      eax, 80070000h
0x180014061  xorps   xmm0, xmm0
0x180014064  movups  [rbp+57h+var_88], xmm0
0x180014068  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001406f  mov     [rbp+57h+pExceptionObject], rcx
0x180014073  mov     [rbp+57h+var_78], eax
0x180014076  mov     [rbp+57h+var_74], 0E3h
0x18001407d  mov     [rbp+57h+var_70], 1
0x180014084  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001408b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001408f  call    _CxxThrowException_0
0x180014095  lock inc cs:dword_180145058
0x18001409c  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800140a3  mov     [rbx], rax
0x1800140a6  mov     [rbp+57h+var_A0], 1
0x1800140ad  mov     ecx, 76h ; 'v'; dwBytes
0x1800140b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800140b7  mov     r14, rax
0x1800140ba  mov     qword ptr [rax], 33h ; '3'
0x1800140c1  mov     dword ptr [rax+8], 1
0x1800140c8  mov     [rax+0Ch], r13w
0x1800140cd  mov     rdx, [rbx]
0x1800140d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800140d4  test    rdx, rdx
0x1800140d7  jz      short loc_1800140F2
0x1800140d9  mov     ecx, edi
0x1800140db  lock xadd [rdx+8], ecx
0x1800140e0  add     ecx, edi
0x1800140e2  jnz     short loc_1800140EF
0x1800140e4  lea     edx, [rdi+11h]; unsigned __int64
0x1800140e7  mov     rcx, [rbx]; void *
0x1800140ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800140ef  mov     [rbx], r13
0x1800140f2  mov     [rbx], r14
0x1800140f5  mov     r8d, 32h ; '2'; cchBufferLength
0x1800140fb  lea     rdx, [r14+0Ch]; lpszVolumeName
0x1800140ff  mov     rcx, r12; lpszVolumeMountPoint
0x180014102  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180014108  test    eax, eax
0x18001410a  jnz     short loc_180014183
0x18001410c  call    cs:__imp_GetLastError
0x180014112  mov     ebx, eax
0x180014114  lea     rax, WPP_GLOBAL_Control
0x18001411b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014122  cmp     rcx, rax
0x180014125  jz      short loc_180014145
0x180014127  test    byte ptr [rcx+1Ch], 4
0x18001412b  jz      short loc_180014145
0x18001412d  mov     edx, 0Dh
0x180014132  mov     r9d, ebx
0x180014135  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18001413c  mov     rcx, [rcx+10h]
0x180014140  call    WPP_SF_d
0x180014145  test    ebx, ebx
0x180014147  jle     short loc_180014152
0x180014149  movzx   ebx, bx
0x18001414c  or      ebx, 80070000h
0x180014152  xorps   xmm0, xmm0
0x180014155  movups  [rbp+57h+var_88], xmm0
0x180014159  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180014160  mov     [rbp+57h+pExceptionObject], rcx
0x180014164  mov     [rbp+57h+var_78], ebx
0x180014167  mov     [rbp+57h+var_74], r13d
0x18001416b  mov     [rbp+57h+var_70], 1
0x180014172  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180014179  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001417d  call    _CxxThrowException_0
0x180014183  mov     rax, [rbx]
0x180014186  inc     rdi
0x180014189  cmp     [rax+rdi*2+0Ch], r13w
0x18001418f  jnz     short loc_180014186
0x180014191  mov     [rax], rdi
0x180014194  mov     rdx, [rbp+57h+arg_18]
0x180014198  mov     rdx, [rdx]; Token
0x18001419b  xor     ecx, ecx; Thread
0x18001419d  call    cs:__imp_SetThreadToken
0x1800141a3  lea     rcx, [rbp+57h+arg_18]; this
0x1800141a7  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x1800141ac  mov     rax, rbx
0x1800141af  add     rsp, 90h
0x1800141b6  pop     r15
0x1800141b8  pop     r14
0x1800141ba  pop     r13
0x1800141bc  pop     r12
0x1800141be  pop     rdi
0x1800141bf  pop     rbx
0x1800141c0  pop     rbp
0x1800141c1  retn
```
