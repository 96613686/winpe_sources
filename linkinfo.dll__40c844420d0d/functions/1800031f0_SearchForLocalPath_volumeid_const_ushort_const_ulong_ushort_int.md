# SearchForLocalPath(_volumeid const *,ushort const *,ulong,ushort *,int)

- ea: `0x1800031f0`
- end: `0x1800033b2`
- name: `?SearchForLocalPath@@YAHPEBU_volumeid@@PEBGKPEAGH@Z`
- size: `450`
- prototype: `__int64 __fastcall(const struct _volumeid *, const unsigned __int16 *, unsigned int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001840`

## callees

- `0x180001ae0`
- `0x180001b60`
- `0x1800031f0`
- `0x1800033c0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003353`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180003353`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800032b9`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x1800032b9`

## pseudocode

```c
_BOOL8 __fastcall SearchForLocalPath(
        const struct _volumeid *a1,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 *a4)
{
  int v5; // ebp
  unsigned __int16 v10; // di
  DWORD LogicalDrives; // r8d
  unsigned int i; // r12d
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  __int64 v15; // r9
  WCHAR *p_RootPathName; // r8
  int v17; // edi
  WCHAR *v18; // rcx
  unsigned __int16 v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+24h] [rbp-54h] BYREF
  DWORD v21; // [rsp+28h] [rbp-50h]
  WCHAR RootPathName; // [rsp+30h] [rbp-48h] BYREF

  v5 = 0;
  v20 = 0;
  if ( !(unsigned int)IsLocalDrivePath(a2) )
    goto LABEL_9;
  if ( !(unsigned int)IsPathOnVolume(a2, a1, &v20) )
    return 0;
  v5 = v20;
  if ( v20 )
  {
    StringCchCopyW(a4, 0x104u, a2);
  }
  else
  {
LABEL_9:
    if ( (a3 & 1) != 0 )
    {
      v10 = *a2;
      v19 = *a2;
      StringCchCopyW(a4, 0x104u, a2);
      LogicalDrives = GetLogicalDrives();
      v21 = LogicalDrives;
      for ( i = 0; i < 0x1A; ++i )
      {
        if ( (LogicalDrives & (1 << i)) == 1 << i && (_WORD)i + 65 != v10 )
        {
          v13 = 2147483646;
          v14 = L"A:\\";
          v15 = 4;
          p_RootPathName = &RootPathName;
          do
          {
            if ( !v13 )
              break;
            if ( !*v14 )
              break;
            *p_RootPathName++ = *v14++;
            --v13;
            --v15;
          }
          while ( v15 );
          v17 = *((_DWORD *)a1 + 1);
          v18 = p_RootPathName - 1;
          if ( v15 )
            v18 = p_RootPathName;
          *v18 = 0;
          RootPathName = i + 65;
          if ( GetDriveTypeW(&RootPathName) == v17 )
          {
            if ( !(unsigned int)IsPathOnVolume(&RootPathName, a1, &v20) )
              return 0;
            v5 = v20;
            if ( v20 )
            {
              StringCchCopyW(a4, 0x104u, a2);
              *a4 = i + 65;
              break;
            }
          }
          LogicalDrives = v21;
          v10 = v19;
        }
      }
    }
  }
  return v5 != 0;
}

```

## disassembly

```asm
0x1800031f0  mov     [rsp+arg_0], rbx
0x1800031f5  push    rbp
0x1800031f6  push    rsi
0x1800031f7  push    rdi
0x1800031f8  push    r12
0x1800031fa  push    r13
0x1800031fc  push    r14
0x1800031fe  push    r15
0x180003200  sub     rsp, 40h
0x180003204  mov     rax, cs:__security_cookie
0x18000320b  xor     rax, rsp
0x18000320e  mov     [rsp+78h+var_40], rax
0x180003213  mov     r14, rcx
0x180003216  xor     ebp, ebp
0x180003218  mov     rcx, rdx; unsigned __int16 *
0x18000321b  mov     [rsp+78h+var_54], ebp
0x18000321f  mov     r15, r9
0x180003222  mov     edi, r8d
0x180003225  mov     rbx, rdx
0x180003228  call    ?IsLocalDrivePath@@YAHPEBG@Z; IsLocalDrivePath(ushort const *)
0x18000322d  test    eax, eax
0x18000322f  jz      short loc_180003296
0x180003231  lea     r8, [rsp+78h+var_54]; int *
0x180003236  mov     rdx, r14; struct _ivolumeidW *
0x180003239  mov     rcx, rbx; unsigned __int16 *
0x18000323c  call    ?IsPathOnVolume@@YAHPEBGPEBU_ivolumeidW@@PEAH@Z; IsPathOnVolume(ushort const *,_ivolumeidW const *,int *)
0x180003241  mov     esi, eax
0x180003243  test    eax, eax
0x180003245  jz      short loc_18000326E
0x180003247  mov     ebp, [rsp+78h+var_54]
0x18000324b  test    ebp, ebp
0x18000324d  jz      short loc_18000329B
0x18000324f  mov     r8, rbx; unsigned __int16 *
0x180003252  mov     edx, 104h; unsigned __int64
0x180003257  mov     rcx, r15; unsigned __int16 *
0x18000325a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000325f  test    ebp, ebp
0x180003261  jz      short loc_18000326E
0x180003263  mov     eax, 1
0x180003268  jmp     short loc_180003270
0x18000326a  test    esi, esi
0x18000326c  jnz     short loc_18000325F
0x18000326e  xor     eax, eax
0x180003270  mov     rcx, [rsp+78h+var_40]
0x180003275  xor     rcx, rsp; StackCookie
0x180003278  call    __security_check_cookie
0x18000327d  mov     rbx, [rsp+78h+arg_0]
0x180003285  add     rsp, 40h
0x180003289  pop     r15
0x18000328b  pop     r14
0x18000328d  pop     r13
0x18000328f  pop     r12
0x180003291  pop     rdi
0x180003292  pop     rsi
0x180003293  pop     rbp
0x180003294  retn
0x180003296  mov     esi, 1
0x18000329b  test    dil, 1
0x18000329f  jz      short loc_18000325F
0x1800032a1  movzx   edi, word ptr [rbx]
0x1800032a4  mov     r8, rbx; unsigned __int16 *
0x1800032a7  mov     edx, 104h; unsigned __int64
0x1800032ac  mov     [rsp+78h+var_58], di
0x1800032b1  mov     rcx, r15; unsigned __int16 *
0x1800032b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800032b9  call    cs:__imp_GetLogicalDrives
0x1800032c0  nop     dword ptr [rax+rax+00h]
0x1800032c5  mov     r8d, eax
0x1800032c8  mov     [rsp+78h+var_50], eax
0x1800032cc  xor     r12d, r12d
0x1800032cf  cmp     r12d, 1Ah
0x1800032d3  jnb     short loc_18000326A
0x1800032d5  mov     ecx, r12d
0x1800032d8  mov     edx, 1
0x1800032dd  shl     edx, cl
0x1800032df  mov     eax, edx
0x1800032e1  and     eax, r8d
0x1800032e4  cmp     eax, edx
0x1800032e6  jnz     loc_1800033AA
0x1800032ec  lea     r13d, [r12+41h]
0x1800032f1  cmp     r13w, di
0x1800032f5  jz      loc_1800033AA
0x1800032fb  mov     ecx, 7FFFFFFEh
0x180003300  lea     rdx, aA; "A:\\"
0x180003307  mov     r9d, 4
0x18000330d  lea     r8, [rsp+78h+RootPathName]
0x180003312  test    rcx, rcx
0x180003315  jz      short loc_180003334
0x180003317  movzx   eax, word ptr [rdx]
0x18000331a  test    ax, ax
0x18000331d  jz      short loc_180003334
0x18000331f  mov     [r8], ax
0x180003323  add     rdx, 2
0x180003327  add     r8, 2
0x18000332b  dec     rcx
0x18000332e  sub     r9, 1
0x180003332  jnz     short loc_180003312
0x180003334  mov     edi, [r14+4]
0x180003338  lea     rcx, [r8-2]
0x18000333c  test    r9, r9
0x18000333f  cmovnz  rcx, r8
0x180003343  xor     eax, eax
0x180003345  mov     [rcx], ax
0x180003348  lea     rcx, [rsp+78h+RootPathName]; lpRootPathName
0x18000334d  mov     [rsp+78h+RootPathName], r13w
0x180003353  call    cs:__imp_GetDriveTypeW
0x18000335a  nop     dword ptr [rax+rax+00h]
0x18000335f  cmp     eax, edi
0x180003361  jnz     short loc_1800033A0
0x180003363  lea     r8, [rsp+78h+var_54]; int *
0x180003368  mov     rdx, r14; struct _ivolumeidW *
0x18000336b  lea     rcx, [rsp+78h+RootPathName]; unsigned __int16 *
0x180003370  call    ?IsPathOnVolume@@YAHPEBGPEBU_ivolumeidW@@PEAH@Z; IsPathOnVolume(ushort const *,_ivolumeidW const *,int *)
0x180003375  mov     esi, eax
0x180003377  test    eax, eax
0x180003379  jz      loc_18000326E
0x18000337f  mov     ebp, [rsp+78h+var_54]
0x180003383  test    ebp, ebp
0x180003385  jz      short loc_1800033A0
0x180003387  mov     r8, rbx; unsigned __int16 *
0x18000338a  mov     edx, 104h; unsigned __int64
0x18000338f  mov     rcx, r15; unsigned __int16 *
0x180003392  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003397  mov     [r15], r13w
0x18000339b  jmp     loc_18000325F
0x1800033a0  mov     r8d, [rsp+78h+var_50]
0x1800033a5  movzx   edi, [rsp+78h+var_58]
0x1800033aa  inc     r12d
0x1800033ad  jmp     loc_1800032CF
```
