# GetDisplayData(void *,ushort const *,ushort const *,ulong *,uchar *,ulong,ulong *)

- ea: `0x18001f720`
- end: `0x18001f8b5`
- name: `?GetDisplayData@@YAKPEAXPEBG1PEAKPEAEK2@Z`
- size: `405`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int *@<r9>, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800098b0`
- `0x18001f720`
- `0x180029f14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f775`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f775`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f834`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f886`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f834`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f886`

## pseudocode

```c
__int64 __fastcall GetDisplayData(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int8 *lpData,
        unsigned int a6,
        unsigned int *lpcbData)
{
  LSTATUS Value; // eax
  unsigned int v10; // edi
  __int64 v11; // rsi
  const unsigned __int16 *FilenameFromPath; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rsi
  DWORD Type[22]; // [rsp+30h] [rbp-58h] BYREF

  Type[0] = 0;
  *lpcbData = a6;
  if ( lpData )
    *lpData = 0;
  Value = RegQueryValueExW(hKey, a3, 0, Type, lpData, lpcbData);
  v10 = Value;
  if ( !Value || Value == 234 )
  {
    if ( Type[0] == 1 )
    {
      v11 = -1;
      if ( lpData )
      {
        *(_WORD *)&lpData[2 * ((unsigned __int64)a6 >> 1) - 2] = 0;
        FilenameFromPath = GetFilenameFromPath((LPCWSTR)lpData);
        if ( FilenameFromPath && FilenameFromPath != (const unsigned __int16 *)lpData )
          StringCchCopyW((unsigned __int16 *)lpData, (unsigned __int64)a6 >> 1, FilenameFromPath);
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&lpData[2 * v13] );
        *lpcbData = 2 * v13 + 2;
      }
      *lpcbData += 2;
      if ( a6 >= *lpcbData && lpData )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&lpData[2 * v14] );
        *(_WORD *)&lpData[2 * v14 + 2] = 0;
        do
          ++v11;
        while ( *(_WORD *)&lpData[2 * v11] );
        RegSetValueExW(hKey, a3, 0, 7u, lpData, 2 * v11 + 4);
      }
    }
    else if ( *lpcbData == 1 && (!lpData || *lpData) )
    {
      if ( a6 >= 0x104 && lpData )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&lpData[2 * v15] );
        RegSetValueExW(hKey, a3, 0, 7u, lpData, 2 * v15 + 4);
      }
      *lpcbData = 260;
    }
    if ( !v10 && *lpcbData > a6 )
      return 234;
  }
  return v10;
}

```

## disassembly

```asm
0x18001f720  push    rbx
0x18001f722  push    rbp
0x18001f723  push    rsi
0x18001f724  push    rdi
0x18001f725  push    r12
0x18001f727  push    r13
0x18001f729  push    r14
0x18001f72b  push    r15
0x18001f72d  sub     rsp, 48h
0x18001f731  mov     r14, [rsp+88h+arg_30]
0x18001f739  xor     ebp, ebp
0x18001f73b  mov     rbx, [rsp+88h+arg_20]
0x18001f743  mov     r12, r8
0x18001f746  mov     r15d, [rsp+88h+arg_28]
0x18001f74e  mov     r13, rcx
0x18001f751  mov     [rsp+88h+Type], ebp
0x18001f755  mov     [r14], r15d
0x18001f758  test    rbx, rbx
0x18001f75b  jz      short loc_18001F760
0x18001f75d  mov     [rbx], bpl
0x18001f760  mov     [rsp+88h+lpcbData], r14; lpcbData
0x18001f765  lea     r9, [rsp+88h+Type]; lpType
0x18001f76a  xor     r8d, r8d; lpReserved
0x18001f76d  mov     [rsp+88h+lpData], rbx; lpData
0x18001f772  mov     rdx, r12; lpValueName
0x18001f775  call    cs:__imp_RegQueryValueExW
0x18001f77b  mov     edi, eax
0x18001f77d  test    eax, eax
0x18001f77f  jz      short loc_18001F78C
0x18001f781  cmp     eax, 0EAh
0x18001f786  jnz     loc_18001F8A2
0x18001f78c  cmp     [rsp+88h+Type], 1
0x18001f791  jnz     loc_18001F83C
0x18001f797  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f79b  test    rbx, rbx
0x18001f79e  jz      short loc_18001F7E5
0x18001f7a0  xor     eax, eax
0x18001f7a2  mov     rbp, r15
0x18001f7a5  shr     rbp, 1
0x18001f7a8  mov     rcx, rbx; lpStringSource
0x18001f7ab  mov     [rbx+rbp*2-2], ax
0x18001f7b0  call    GetFilenameFromPath
0x18001f7b5  test    rax, rax
0x18001f7b8  jz      short loc_18001F7CD
0x18001f7ba  cmp     rax, rbx
0x18001f7bd  jz      short loc_18001F7CD
0x18001f7bf  mov     r8, rax; unsigned __int16 *
0x18001f7c2  mov     rdx, rbp; unsigned __int64
0x18001f7c5  mov     rcx, rbx; unsigned __int16 *
0x18001f7c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f7cd  mov     rax, rsi
0x18001f7d0  xor     ebp, ebp
0x18001f7d2  inc     rax
0x18001f7d5  cmp     [rbx+rax*2], bp
0x18001f7d9  jnz     short loc_18001F7D2
0x18001f7db  lea     eax, ds:2[rax*2]
0x18001f7e2  mov     [r14], eax
0x18001f7e5  add     dword ptr [r14], 2
0x18001f7e9  cmp     r15d, [r14]
0x18001f7ec  jb      loc_18001F893
0x18001f7f2  test    rbx, rbx
0x18001f7f5  jz      loc_18001F893
0x18001f7fb  mov     rcx, rsi
0x18001f7fe  inc     rcx
0x18001f801  cmp     [rbx+rcx*2], bp
0x18001f805  jnz     short loc_18001F7FE
0x18001f807  mov     [rbx+rcx*2+2], bp
0x18001f80c  inc     rsi
0x18001f80f  cmp     [rbx+rsi*2], bp
0x18001f813  jnz     short loc_18001F80C
0x18001f815  lea     eax, ds:4[rsi*2]
0x18001f81c  mov     r9d, 7; dwType
0x18001f822  mov     dword ptr [rsp+88h+lpcbData], eax; cbData
0x18001f826  xor     r8d, r8d; Reserved
0x18001f829  mov     rdx, r12; lpValueName
0x18001f82c  mov     [rsp+88h+lpData], rbx; lpData
0x18001f831  mov     rcx, r13; hKey
0x18001f834  call    cs:__imp_RegSetValueExW
0x18001f83a  jmp     short loc_18001F893
0x18001f83c  cmp     dword ptr [r14], 1
0x18001f840  jnz     short loc_18001F893
0x18001f842  test    rbx, rbx
0x18001f845  jz      short loc_18001F84C
0x18001f847  cmp     [rbx], bpl
0x18001f84a  jz      short loc_18001F893
0x18001f84c  cmp     r15d, 104h
0x18001f853  jb      short loc_18001F88C
0x18001f855  test    rbx, rbx
0x18001f858  jz      short loc_18001F88C
0x18001f85a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001f85e  inc     rsi
0x18001f861  cmp     [rbx+rsi*2], bp
0x18001f865  jnz     short loc_18001F85E
0x18001f867  lea     eax, ds:4[rsi*2]
0x18001f86e  mov     r9d, 7; dwType
0x18001f874  mov     dword ptr [rsp+88h+lpcbData], eax; cbData
0x18001f878  xor     r8d, r8d; Reserved
0x18001f87b  mov     rdx, r12; lpValueName
0x18001f87e  mov     [rsp+88h+lpData], rbx; lpData
0x18001f883  mov     rcx, r13; hKey
0x18001f886  call    cs:__imp_RegSetValueExW
0x18001f88c  mov     dword ptr [r14], 104h
0x18001f893  test    edi, edi
0x18001f895  jnz     short loc_18001F8A2
0x18001f897  cmp     [r14], r15d
0x18001f89a  mov     eax, 0EAh
0x18001f89f  cmova   edi, eax
0x18001f8a2  mov     eax, edi
0x18001f8a4  add     rsp, 48h
0x18001f8a8  pop     r15
0x18001f8aa  pop     r14
0x18001f8ac  pop     r13
0x18001f8ae  pop     r12
0x18001f8b0  pop     rdi
0x18001f8b1  pop     rsi
0x18001f8b2  pop     rbp
0x18001f8b3  pop     rbx
0x18001f8b4  retn
```
