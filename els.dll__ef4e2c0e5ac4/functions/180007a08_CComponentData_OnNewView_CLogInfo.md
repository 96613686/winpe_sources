# CComponentData::_OnNewView(CLogInfo *)

- ea: `0x180007a08`
- end: `0x180007bd2`
- name: `?_OnNewView@CComponentData@@AEAAJPEAVCLogInfo@@@Z`
- size: `458`
- prototype: `int(CComponentData *__hidden this, struct CLogInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180002928`
- `0x180007060`
- `0x180007a08`
- `0x180015e48`
- `0x18001673c`
- `0x180016a98`
- `0x180017630`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007ae8`
- `msvcrt!_wcsicmp` at `0x180007ae8`

## pseudocode

```c
__int64 __fastcall CComponentData::_OnNewView(CComponentData *this, struct CLogInfo *a2)
{
  int v2; // esi
  CLogInfo *v5; // rax
  CLogInfo *v6; // rdi
  __int64 v7; // r15
  int v8; // r12d
  int v9; // ebx
  unsigned __int16 *DisplayName; // rax
  CLogInfo *i; // rbx
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-E0h]
  _QWORD v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+44h] [rbp-BCh]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  CLogInfo *v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  CLogInfo *v23; // [rsp+68h] [rbp-98h]
  wchar_t String2[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  if ( (*((_BYTE *)this + 56) & 4) == 0 )
  {
    v5 = (CLogInfo *)operator new(0x1318u);
    v23 = v5;
    if ( v5 && (v6 = CLogInfo::CLogInfo(v5, a2)) != 0 )
    {
      *((_WORD *)v6 + 12) |= 0x108u;
      v7 = *((_QWORD *)a2 + 608);
      if ( v7 )
        CLogSet::AddLogInfoToList(*((CLogSet **)a2 + 608), v6);
      v8 = 2;
LABEL_7:
      v9 = v8++;
      DisplayName = CLogInfo::GetDisplayName(v6);
      LODWORD(v15) = v9;
      StringCchPrintfW(String2, 0x104u, L"%.200ws (%u)", DisplayName, v15);
      for ( i = *(CLogInfo **)(v7 + 136); i; i = (CLogInfo *)*((_QWORD *)i + 1) )
      {
        v12 = CLogInfo::GetDisplayName(i);
        if ( !_wcsicmp(v12, String2) )
          goto LABEL_7;
      }
      CLogInfo::SetDisplayName(v6, String2);
      if ( *((_QWORD *)this + 142) )
      {
        v21 = *((_QWORD *)this + 142);
        v16[0] = 110;
        v19 = 0;
        v22 = 0;
        if ( (*((_WORD *)v6 + 12) & 0x200) != 0 )
        {
          v17 = 2;
          v18 = 2;
        }
        else
        {
          v17 = 0;
          v18 = 1;
        }
        v13 = *((_QWORD *)this + 145);
        v16[1] = -1;
        v20 = v6;
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v13 + 24LL))(v13, v16);
        *((_QWORD *)v6 + 607) = v22;
        if ( v2 >= 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 144) + 88LL))(*((_QWORD *)this + 144));
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007a08  mov     [rsp-8+arg_10], rbx
0x180007a0d  mov     [rsp-8+arg_18], rsi
0x180007a12  push    rbp
0x180007a13  push    rdi
0x180007a14  push    r12
0x180007a16  push    r14
0x180007a18  push    r15
0x180007a1a  lea     rbp, [rsp-190h]
0x180007a22  sub     rsp, 290h
0x180007a29  mov     rax, cs:__security_cookie
0x180007a30  xor     rax, rsp
0x180007a33  mov     [rbp+1B0h+var_30], rax
0x180007a3a  xor     esi, esi
0x180007a3c  mov     rbx, rdx
0x180007a3f  test    byte ptr [rcx+38h], 4
0x180007a43  mov     r14, rcx
0x180007a46  jnz     loc_180007BA5
0x180007a4c  mov     ecx, 1318h; Size
0x180007a51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a56  mov     [rsp+2B0h+var_248], rax
0x180007a5b  test    rax, rax
0x180007a5e  jz      loc_180007BA0
0x180007a64  mov     rdx, rbx; struct CLogInfo *
0x180007a67  mov     rcx, rax; this
0x180007a6a  call    ??0CLogInfo@@QEAA@PEBV0@@Z; CLogInfo::CLogInfo(CLogInfo const *)
0x180007a6f  mov     rdi, rax
0x180007a72  test    rax, rax
0x180007a75  jz      loc_180007BA0
0x180007a7b  mov     eax, 108h
0x180007a80  or      [rdi+18h], ax
0x180007a84  mov     r15, [rbx+1300h]
0x180007a8b  test    r15, r15
0x180007a8e  jz      short loc_180007A9B
0x180007a90  mov     rdx, rdi; struct CLogInfo *
0x180007a93  mov     rcx, r15; this
0x180007a96  call    ?AddLogInfoToList@CLogSet@@QEAAXPEAVCLogInfo@@@Z; CLogSet::AddLogInfoToList(CLogInfo *)
0x180007a9b  mov     r12d, 2
0x180007aa1  mov     ebx, r12d
0x180007aa4  mov     rcx, rdi; this
0x180007aa7  inc     r12d
0x180007aaa  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x180007aaf  mov     r9, rax
0x180007ab2  mov     [rsp+2B0h+var_290], ebx
0x180007ab6  lea     r8, a200wsU; "%.200ws (%u)"
0x180007abd  mov     edx, 104h; unsigned __int64
0x180007ac2  lea     rcx, [rsp+2B0h+String2]; unsigned __int16 *
0x180007ac7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007acc  mov     rbx, [r15+88h]
0x180007ad3  test    rbx, rbx
0x180007ad6  jz      short loc_180007AF8
0x180007ad8  mov     rcx, rbx; this
0x180007adb  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x180007ae0  mov     rcx, rax; String1
0x180007ae3  lea     rdx, [rsp+2B0h+String2]; String2
0x180007ae8  call    cs:__imp__wcsicmp
0x180007aee  test    eax, eax
0x180007af0  jz      short loc_180007AA1
0x180007af2  mov     rbx, [rbx+8]
0x180007af6  jmp     short loc_180007AD3
0x180007af8  lea     rdx, [rsp+2B0h+String2]; unsigned __int16 *
0x180007afd  mov     rcx, rdi; this
0x180007b00  call    ?SetDisplayName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetDisplayName(ushort const *)
0x180007b05  mov     rax, [r14+470h]
0x180007b0c  test    rax, rax
0x180007b0f  jz      loc_180007BA5
0x180007b15  mov     [rsp+2B0h+var_258], rax
0x180007b1a  mov     eax, 200h
0x180007b1f  mov     [rsp+2B0h+var_280], 6Eh ; 'n'
0x180007b28  mov     [rsp+2B0h+var_268], rsi
0x180007b2d  mov     [rsp+2B0h+var_250], rsi
0x180007b32  test    [rdi+18h], ax
0x180007b36  jz      short loc_180007B47
0x180007b38  mov     eax, 2
0x180007b3d  mov     [rsp+2B0h+var_270], eax
0x180007b41  mov     [rsp+2B0h+var_26C], eax
0x180007b45  jmp     short loc_180007B53
0x180007b47  mov     [rsp+2B0h+var_270], esi
0x180007b4b  mov     [rsp+2B0h+var_26C], 1
0x180007b53  mov     rcx, [r14+488h]
0x180007b5a  lea     rdx, [rsp+2B0h+var_280]
0x180007b5f  mov     [rsp+2B0h+var_278], 0FFFFFFFFFFFFFFFFh
0x180007b68  mov     [rsp+2B0h+var_260], rdi
0x180007b6d  mov     rax, [rcx]
0x180007b70  mov     rax, [rax+18h]
0x180007b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b79  mov     rdx, [rsp+2B0h+var_250]
0x180007b7e  mov     esi, eax
0x180007b80  mov     [rdi+12F8h], rdx
0x180007b87  test    eax, eax
0x180007b89  js      short loc_180007BA5
0x180007b8b  mov     rcx, [r14+480h]
0x180007b92  mov     r8, [rcx]
0x180007b95  mov     rax, [r8+58h]
0x180007b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9e  jmp     short loc_180007BA5
0x180007ba0  mov     esi, 8007000Eh
0x180007ba5  mov     eax, esi
0x180007ba7  mov     rcx, [rbp+1B0h+var_30]
0x180007bae  xor     rcx, rsp; StackCookie
0x180007bb1  call    __security_check_cookie
0x180007bb6  lea     r11, [rsp+2B0h+var_20]
0x180007bbe  mov     rbx, [r11+40h]
0x180007bc2  mov     rsi, [r11+48h]
0x180007bc6  mov     rsp, r11
0x180007bc9  pop     r15
0x180007bcb  pop     r14
0x180007bcd  pop     r12
0x180007bcf  pop     rdi
0x180007bd0  pop     rbp
0x180007bd1  retn
```
