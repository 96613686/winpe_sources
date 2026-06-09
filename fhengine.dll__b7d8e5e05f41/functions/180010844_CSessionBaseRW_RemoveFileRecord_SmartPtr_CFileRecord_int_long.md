# CSessionBaseRW::RemoveFileRecord(SmartPtr<CFileRecord>,int,long)

- ea: `0x180010844`
- end: `0x18001090c`
- name: `?RemoveFileRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCFileRecord@@@@HJ@Z`
- size: `200`
- prototype: `__int64 __fastcall(CSessionBaseRW *, _QWORD *, int, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180013e14`
- `0x180016da0`
- `0x180017290`
- `0x180018778`
- `0x18001cb74`

## callees

- `0x180007a9c`
- `0x18000935c`
- `0x18000c450`
- `0x180010844`
- `0x180010b18`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::RemoveFileRecord(CSessionBaseRW *a1, _QWORD *a2, int a3, int a4)
{
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  CFileRecord **v11; // [rsp+48h] [rbp+10h] BYREF

  v6 = CSessionBaseRW::RemoveNamespaceRecordsByFileRecordRef(a1, *(_DWORD *)(*(_QWORD *)*a2 + 16LL), a3, a4);
  if ( v6 >= 0 )
  {
    v9 = *a2;
    v11 = (CFileRecord **)v9;
    if ( v9 )
      ++*(_DWORD *)(v9 + 8);
    v6 = CSessionBaseRW::CleanupFileRecord((__int64)a1, &v11, 0, 0);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 87;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 86;
LABEL_11:
      WPP_SF_dd(
        v7[2],
        v8,
        &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        *(unsigned int *)(*(_QWORD *)*a2 + 16LL),
        v6);
    }
  }
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010844  mov     [rsp+arg_0], rbx
0x180010849  mov     [rsp+arg_10], rsi
0x18001084e  push    rdi
0x18001084f  sub     rsp, 30h
0x180010853  mov     rax, [rdx]
0x180010856  mov     rdi, rdx
0x180010859  mov     rsi, rcx
0x18001085c  mov     rdx, [rax]
0x18001085f  mov     edx, [rdx+10h]; unsigned int
0x180010862  call    ?RemoveNamespaceRecordsByFileRecordRef@CSessionBaseRW@@IEAAJKHJ@Z; CSessionBaseRW::RemoveNamespaceRecordsByFileRecordRef(ulong,int,long)
0x180010867  mov     ebx, eax
0x180010869  test    eax, eax
0x18001086b  jns     short loc_18001088D
0x18001086d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010874  lea     rax, WPP_GLOBAL_Control
0x18001087b  cmp     rcx, rax
0x18001087e  jz      short loc_1800108F2
0x180010880  test    byte ptr [rcx+1Ch], 1
0x180010884  jz      short loc_1800108F2
0x180010886  mov     edx, 56h ; 'V'
0x18001088b  jmp     short loc_1800108D4
0x18001088d  mov     rax, [rdi]
0x180010890  mov     [rsp+38h+arg_8], rax
0x180010895  test    rax, rax
0x180010898  jz      short loc_18001089D
0x18001089a  inc     dword ptr [rax+8]
0x18001089d  xor     r9d, r9d
0x1800108a0  lea     rdx, [rsp+38h+arg_8]
0x1800108a5  xor     r8d, r8d
0x1800108a8  mov     rcx, rsi
0x1800108ab  call    ?CleanupFileRecord@CSessionBaseRW@@IEAAJV?$SmartPtr@VCFileRecord@@@@HH@Z; CSessionBaseRW::CleanupFileRecord(SmartPtr<CFileRecord>,int,int)
0x1800108b0  mov     ebx, eax
0x1800108b2  test    eax, eax
0x1800108b4  jns     short loc_1800108F2
0x1800108b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108bd  lea     rax, WPP_GLOBAL_Control
0x1800108c4  cmp     rcx, rax
0x1800108c7  jz      short loc_1800108F2
0x1800108c9  test    byte ptr [rcx+1Ch], 1
0x1800108cd  jz      short loc_1800108F2
0x1800108cf  mov     edx, 57h ; 'W'
0x1800108d4  mov     rax, [rdi]
0x1800108d7  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x1800108de  mov     rcx, [rcx+10h]
0x1800108e2  mov     [rsp+38h+var_18], ebx
0x1800108e6  mov     r9, [rax]
0x1800108e9  mov     r9d, [r9+10h]
0x1800108ed  call    WPP_SF_dd
0x1800108f2  mov     rcx, rdi
0x1800108f5  call    ??1?$SmartPtr@VCFileRecord@@@@QEAA@XZ; SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(void)
0x1800108fa  mov     rsi, [rsp+38h+arg_10]
0x1800108ff  mov     eax, ebx
0x180010901  mov     rbx, [rsp+38h+arg_0]
0x180010906  add     rsp, 30h
0x18001090a  pop     rdi
0x18001090b  retn
```
