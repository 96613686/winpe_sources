# CMMCWatsonAPI::ExceptionFilter(_EXCEPTION_POINTERS *,int)

- ea: `0x1800124a0`
- end: `0x18001262b`
- name: `?ExceptionFilter@CMMCWatsonAPI@@SAJPEAU_EXCEPTION_POINTERS@@H@Z`
- size: `395`
- prototype: `static int(struct _EXCEPTION_POINTERS *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e04c`
- `0x180012640`
- `0x1800127b0`

## callees

- `0x1800064b4`
- `0x180008630`
- `0x18000bd34`
- `0x18000d870`
- `0x1800124a0`
- `0x180012bf4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180012590`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180012590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001257e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001257e`

## pseudocode

```c
__int64 __fastcall CMMCWatsonAPI::ExceptionFilter(struct _EXCEPTION_POINTERS *a1, int a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rdx
  CMMCWatson *v7; // rbx
  __int64 v8; // rax
  CMMCWatson *v9; // rcx
  const unsigned __int16 *SnapinModuleName; // r8

  v4 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( a1->ExceptionRecord->ExceptionCode == -2147483645 )
    {
      if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control )
        return v4;
      if ( *(_BYTE *)(v5 + 25) < 2u )
        goto LABEL_25;
      v6 = 48;
    }
    else
    {
      v7 = g_pMMCWatson;
      if ( g_pMMCWatson )
      {
        v8 = *((_QWORD *)g_pMMCWatson + 71);
        v4 = -1;
        if ( v8 )
        {
          *(_QWORD *)(v8 + 20) = a1;
          *(_QWORD *)(*((_QWORD *)v7 + 71) + 12LL) = a1->ExceptionRecord->ExceptionAddress;
          *(_DWORD *)(*((_QWORD *)v7 + 71) + 8LL) = GetCurrentThreadId();
          *(_DWORD *)(*((_QWORD *)v7 + 71) + 4448LL) = GetUserDefaultLCID();
          SnapinModuleName = BookKeeping::GetSnapinModuleName(a2);
          if ( SnapinModuleName )
            StringCchCopyW((unsigned __int16 *)(*((_QWORD *)g_pMMCWatson + 71) + 212LL), 0x104u, SnapinModuleName);
          CMMCWatson::LaunchWatson(v9);
          goto LABEL_24;
        }
        if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control )
          return v4;
        if ( *(_BYTE *)(v5 + 25) < 2u )
          goto LABEL_25;
        v6 = 50;
      }
      else
      {
        if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control )
          return v4;
        if ( *(_BYTE *)(v5 + 25) < 2u )
          goto LABEL_25;
        v6 = (unsigned int)((_DWORD)g_pMMCWatson + 49);
      }
    }
LABEL_23:
    WPP_SF_(*(_QWORD *)(v5 + 16), v6, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
LABEL_24:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control )
    return v4;
  if ( *(_BYTE *)(v5 + 25) >= 2u )
  {
    v6 = 47;
    goto LABEL_23;
  }
LABEL_25:
  if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && *(_BYTE *)(v5 + 25) >= 2u )
    WPP_SF_d(*(_QWORD *)(v5 + 16), 51, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800124a0  push    rbx
0x1800124a2  push    rbp
0x1800124a3  push    rsi
0x1800124a4  push    rdi
0x1800124a5  push    r12
0x1800124a7  push    r15
0x1800124a9  sub     rsp, 28h
0x1800124ad  mov     ebp, edx
0x1800124af  mov     rdi, rcx
0x1800124b2  xor     esi, esi
0x1800124b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124bb  lea     r15, WPP_GLOBAL_Control
0x1800124c2  lea     r12, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x1800124c9  cmp     rcx, r15
0x1800124cc  jz      short loc_1800124EA
0x1800124ce  cmp     byte ptr [rcx+19h], 2
0x1800124d2  jb      short loc_1800124EA
0x1800124d4  mov     rcx, [rcx+10h]
0x1800124d8  lea     edx, [rsi+2Eh]
0x1800124db  mov     r8, r12
0x1800124de  call    WPP_SF_
0x1800124e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ea  test    rdi, rdi
0x1800124ed  jnz     short loc_18001250A
0x1800124ef  cmp     rcx, r15
0x1800124f2  jz      loc_18001261C
0x1800124f8  cmp     byte ptr [rcx+19h], 2
0x1800124fc  jb      loc_1800125FD
0x180012502  lea     edx, [rdi+2Fh]
0x180012505  jmp     loc_1800125EA
0x18001250a  mov     rax, [rdi]
0x18001250d  cmp     dword ptr [rax], 80000003h
0x180012513  jnz     short loc_180012532
0x180012515  cmp     rcx, r15
0x180012518  jz      loc_18001261C
0x18001251e  cmp     byte ptr [rcx+19h], 2
0x180012522  jb      loc_1800125FD
0x180012528  mov     edx, 30h ; '0'
0x18001252d  jmp     loc_1800125EA
0x180012532  mov     rbx, cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA; CMMCWatson * g_pMMCWatson
0x180012539  test    rbx, rbx
0x18001253c  jnz     short loc_180012559
0x18001253e  cmp     rcx, r15
0x180012541  jz      loc_18001261C
0x180012547  cmp     byte ptr [rcx+19h], 2
0x18001254b  jb      loc_1800125FD
0x180012551  lea     edx, [rbx+31h]
0x180012554  jmp     loc_1800125EA
0x180012559  mov     rax, [rbx+238h]
0x180012560  or      esi, 0FFFFFFFFh
0x180012563  test    rax, rax
0x180012566  jz      short loc_1800125DA
0x180012568  mov     [rax+14h], rdi
0x18001256c  mov     rax, [rdi]
0x18001256f  mov     rcx, [rbx+238h]
0x180012576  mov     rax, [rax+10h]
0x18001257a  mov     [rcx+0Ch], rax
0x18001257e  call    cs:__imp_GetCurrentThreadId
0x180012584  mov     ecx, eax
0x180012586  mov     rax, [rbx+238h]
0x18001258d  mov     [rax+8], ecx
0x180012590  call    cs:__imp_GetUserDefaultLCID
0x180012596  mov     ecx, eax
0x180012598  mov     rax, [rbx+238h]
0x18001259f  mov     [rax+1160h], ecx
0x1800125a5  mov     ecx, ebp; int
0x1800125a7  call    ?GetSnapinModuleName@BookKeeping@@SAPEBGH@Z; BookKeeping::GetSnapinModuleName(int)
0x1800125ac  mov     r8, rax; unsigned __int16 *
0x1800125af  test    rax, rax
0x1800125b2  jz      short loc_1800125D3
0x1800125b4  mov     rax, cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA; CMMCWatson * g_pMMCWatson
0x1800125bb  mov     edx, 104h; unsigned __int64
0x1800125c0  mov     rcx, [rax+238h]
0x1800125c7  add     rcx, 0D4h; unsigned __int16 *
0x1800125ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800125d3  call    ?LaunchWatson@CMMCWatson@@AEAAXXZ; CMMCWatson::LaunchWatson(void)
0x1800125d8  jmp     short loc_1800125F6
0x1800125da  cmp     rcx, r15
0x1800125dd  jz      short loc_18001261C
0x1800125df  cmp     byte ptr [rcx+19h], 2
0x1800125e3  jb      short loc_1800125FD
0x1800125e5  mov     edx, 32h ; '2'
0x1800125ea  mov     rcx, [rcx+10h]
0x1800125ee  mov     r8, r12
0x1800125f1  call    WPP_SF_
0x1800125f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125fd  cmp     rcx, r15
0x180012600  jz      short loc_18001261C
0x180012602  cmp     byte ptr [rcx+19h], 2
0x180012606  jb      short loc_18001261C
0x180012608  mov     rcx, [rcx+10h]
0x18001260c  mov     edx, 33h ; '3'
0x180012611  mov     r9d, esi
0x180012614  mov     r8, r12
0x180012617  call    WPP_SF_d
0x18001261c  mov     eax, esi
0x18001261e  add     rsp, 28h
0x180012622  pop     r15
0x180012624  pop     r12
0x180012626  pop     rdi
0x180012627  pop     rsi
0x180012628  pop     rbp
0x180012629  pop     rbx
0x18001262a  retn
```
