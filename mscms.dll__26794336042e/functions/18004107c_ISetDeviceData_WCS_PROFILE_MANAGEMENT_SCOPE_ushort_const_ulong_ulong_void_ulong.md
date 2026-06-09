# ISetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,ulong,void *,ulong)

- ea: `0x18004107c`
- end: `0x18004129e`
- name: `?ISetDeviceData@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKKPEAXK@Z`
- size: `546`
- prototype: `__int64 __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004344c`
- `0x1800471b0`

## callees

- `0x180020fd8`
- `0x180029d1c`
- `0x18004107c`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004114f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004114f`

## string_xrefs

- `0x18004122e`: `mscms.dll`
- `0x18004120f`: `Directory`

## pseudocode

```c
__int64 __fastcall ISetDeviceData(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned int v10; // edi
  unsigned int v11; // ebx
  unsigned int (__fastcall *v12)(__int64, __int64, wchar_t *, __int64, unsigned __int16 *, _DWORD); // r12
  __int64 v13; // r13
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v17; // [rsp+40h] [rbp-49h] BYREF
  unsigned int (__fastcall *v18)(const unsigned __int16 *, __int64 *, __int128 *, _QWORD); // [rsp+48h] [rbp-41h] BYREF
  unsigned int (__fastcall *v19)(__int64, __int64, wchar_t *, __int64, unsigned __int16 *, _DWORD); // [rsp+50h] [rbp-39h] BYREF
  wchar_t *v20; // [rsp+58h] [rbp-31h] BYREF
  __int64 v21; // [rsp+60h] [rbp-29h] BYREF
  void (*v22)(void); // [rsp+68h] [rbp-21h] BYREF
  __int128 v23; // [rsp+70h] [rbp-19h] BYREF
  __int64 v24; // [rsp+80h] [rbp-9h]

  v24 = 0;
  v18 = 0;
  v22 = 0;
  v19 = 0;
  v17 = 0;
  v21 = 0;
  v20 = 0;
  v23 = 0;
  v10 = 0;
  if ( !(unsigned int)GetDeviceDataAccessFunctions(a1, a3, (unsigned int)&v18, (unsigned int)&v22, 0, (__int64)&v19)
    || !(unsigned int)GetDeviceDataLocation(a3, a4, &v21, &v20) )
  {
    goto LABEL_24;
  }
  v11 = 4;
  if ( a3 == 1886549106 )
  {
    *((_QWORD *)&v23 + 1) = 0;
    *(_QWORD *)&v23 = L"RAW";
    LODWORD(v24) = 4;
  }
  if ( a4 != 1 )
  {
    if ( a4 == 2 )
    {
      v11 = 3;
      goto LABEL_13;
    }
    if ( a4 == 3 )
      goto LABEL_13;
    if ( a4 != 4 && a4 - 5 >= 2 )
    {
      SetLastError(0x57u);
      goto LABEL_24;
    }
  }
  v11 = 7;
LABEL_13:
  if ( v18(a2, &v17, &v23, 0) )
  {
    v12 = v19;
    v13 = v21;
    if ( !v19(v17, v21, v20, v11, a5, a6) )
    {
      v10 = 1;
      if ( a3 == 1886549106 && ((a4 - 1) & 0xFFFFFFFB) == 0 && a1 == WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( gszColorDir[v15] );
        if ( v12(v17, v13, gszDirectory, 1, gszColorDir, 2 * v15 + 2) )
          goto LABEL_23;
        do
          ++v14;
        while ( gszMSCMS[v14] );
        if ( v12(v17, v13, gszModule, 1, gszMSCMS, 2 * v14 + 2) )
LABEL_23:
          v10 = 0;
      }
    }
  }
LABEL_24:
  if ( v17 )
    v22();
  return v10;
}

```

## disassembly

```asm
0x18004107c  push    rbp
0x18004107e  push    rbx
0x18004107f  push    rsi
0x180041080  push    rdi
0x180041081  push    r12
0x180041083  push    r13
0x180041085  push    r14
0x180041087  push    r15
0x180041089  lea     rbp, [rsp-0Fh]
0x18004108e  sub     rsp, 98h
0x180041095  xor     r13d, r13d
0x180041098  xor     eax, eax
0x18004109a  mov     esi, r8d
0x18004109d  mov     [rbp+47h+var_50], rax
0x1800410a1  lea     rax, [rbp+47h+var_80]
0x1800410a5  mov     [rbp+47h+var_88], r13
0x1800410a9  mov     r14d, r9d
0x1800410ac  mov     [rsp+0D0h+var_A8], rax
0x1800410b1  mov     r12, rdx
0x1800410b4  mov     [rsp+0D0h+var_B0], r13
0x1800410b9  xorps   xmm0, xmm0
0x1800410bc  mov     [rbp+47h+var_68], r13
0x1800410c0  lea     r9, [rbp+47h+var_68]
0x1800410c4  mov     [rbp+47h+var_80], r13
0x1800410c8  lea     r8, [rbp+47h+var_88]
0x1800410cc  mov     [rbp+47h+var_90], r13
0x1800410d0  mov     edx, esi
0x1800410d2  mov     [rbp+47h+var_70], r13
0x1800410d6  mov     r15d, ecx
0x1800410d9  mov     [rbp+47h+var_78], r13
0x1800410dd  movups  [rbp+47h+var_60], xmm0
0x1800410e1  mov     edi, r13d
0x1800410e4  call    GetDeviceDataAccessFunctions
0x1800410e9  test    eax, eax
0x1800410eb  jz      loc_180041276
0x1800410f1  lea     r9, [rbp+47h+var_78]
0x1800410f5  mov     edx, r14d
0x1800410f8  lea     r8, [rbp+47h+var_70]
0x1800410fc  mov     ecx, esi
0x1800410fe  call    GetDeviceDataLocation
0x180041103  test    eax, eax
0x180041105  jz      loc_180041276
0x18004110b  lea     ebx, [r13+4]
0x18004110f  cmp     esi, 70727472h
0x180041115  jnz     short loc_180041129
0x180041117  lea     rax, aRaw; "RAW"
0x18004111e  mov     qword ptr [rbp+47h+var_60+8], r13
0x180041122  mov     qword ptr [rbp+47h+var_60], rax
0x180041126  mov     dword ptr [rbp+47h+var_50], ebx
0x180041129  mov     eax, r14d
0x18004112c  sub     eax, 1
0x18004112f  jz      short loc_180041161
0x180041131  sub     eax, 1
0x180041134  jz      short loc_18004115A
0x180041136  sub     eax, 1
0x180041139  jz      short loc_180041166
0x18004113b  sub     eax, 1
0x18004113e  jz      short loc_180041161
0x180041140  sub     eax, 1
0x180041143  jz      short loc_180041161
0x180041145  cmp     eax, 1
0x180041148  jz      short loc_180041161
0x18004114a  mov     ecx, 57h ; 'W'; dwErrCode
0x18004114f  call    cs:__imp_SetLastError
0x180041155  jmp     loc_180041276
0x18004115a  mov     ebx, 3
0x18004115f  jmp     short loc_180041166
0x180041161  mov     ebx, 7
0x180041166  mov     rax, [rbp+47h+var_88]
0x18004116a  lea     r8, [rbp+47h+var_60]
0x18004116e  xor     r9d, r9d
0x180041171  lea     rdx, [rbp+47h+var_90]
0x180041175  mov     rcx, r12
0x180041178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004117d  test    eax, eax
0x18004117f  jz      loc_180041276
0x180041185  mov     eax, [rbp+47h+arg_28]
0x180041188  mov     r9d, ebx
0x18004118b  mov     r12, [rbp+47h+var_80]
0x18004118f  mov     r13, [rbp+47h+var_70]
0x180041193  mov     r8, [rbp+47h+var_78]
0x180041197  mov     rdx, r13
0x18004119a  mov     rcx, [rbp+47h+var_90]
0x18004119e  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800411a2  mov     rax, [rbp+47h+arg_20]
0x1800411a6  mov     [rsp+0D0h+var_B0], rax
0x1800411ab  mov     rax, r12
0x1800411ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411b3  test    eax, eax
0x1800411b5  jz      short loc_1800411BF
0x1800411b7  xor     r13d, r13d
0x1800411ba  jmp     loc_180041276
0x1800411bf  mov     edi, 1
0x1800411c4  cmp     esi, 70727472h
0x1800411ca  jnz     loc_180041276
0x1800411d0  lea     eax, [r14-1]
0x1800411d4  test    eax, 0FFFFFFFBh
0x1800411d9  jnz     loc_180041276
0x1800411df  xor     esi, esi
0x1800411e1  test    r15d, r15d
0x1800411e4  jnz     loc_180041276
0x1800411ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800411ee  lea     rcx, gszColorDir; "COLOR"
0x1800411f5  mov     rax, rbx
0x1800411f8  inc     rax
0x1800411fb  cmp     [rcx+rax*2], si
0x1800411ff  jnz     short loc_1800411F8
0x180041201  lea     eax, ds:2[rax*2]
0x180041208  mov     r9d, edi
0x18004120b  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18004120f  lea     r8, gszDirectory; "Directory"
0x180041216  mov     [rsp+0D0h+var_B0], rcx
0x18004121b  mov     rdx, r13
0x18004121e  mov     rcx, [rbp+47h+var_90]
0x180041222  mov     rax, r12
0x180041225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004122a  test    eax, eax
0x18004122c  jnz     short loc_180041270
0x18004122e  lea     rcx, gszMSCMS; "mscms.dll"
0x180041235  inc     rbx
0x180041238  cmp     [rcx+rbx*2], si
0x18004123c  jnz     short loc_180041235
0x18004123e  lea     eax, ds:2[rbx*2]
0x180041245  mov     r9d, edi
0x180041248  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18004124c  lea     r8, gszModule; "Module"
0x180041253  mov     [rsp+0D0h+var_B0], rcx
0x180041258  mov     rdx, r13
0x18004125b  mov     rcx, [rbp+47h+var_90]
0x18004125f  mov     rax, r12
0x180041262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041267  xor     r13d, r13d
0x18004126a  test    eax, eax
0x18004126c  jz      short loc_180041276
0x18004126e  jmp     short loc_180041273
0x180041270  xor     r13d, r13d
0x180041273  mov     edi, r13d
0x180041276  mov     rcx, [rbp+47h+var_90]
0x18004127a  test    rcx, rcx
0x18004127d  jz      short loc_180041288
0x18004127f  mov     rax, [rbp+47h+var_68]
0x180041283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041288  mov     eax, edi
0x18004128a  add     rsp, 98h
0x180041291  pop     r15
0x180041293  pop     r14
0x180041295  pop     r13
0x180041297  pop     r12
0x180041299  pop     rdi
0x18004129a  pop     rsi
0x18004129b  pop     rbx
0x18004129c  pop     rbp
0x18004129d  retn
```
