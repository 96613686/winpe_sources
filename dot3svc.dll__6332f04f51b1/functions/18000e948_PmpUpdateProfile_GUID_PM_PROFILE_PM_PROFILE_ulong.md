# PmpUpdateProfile(_GUID *,_PM_PROFILE *,_PM_PROFILE *,ulong)

- ea: `0x18000e948`
- end: `0x18000ebf7`
- name: `?PmpUpdateProfile@@YAKPEAU_GUID@@PEAU_PM_PROFILE@@1K@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _GUID *, struct _PM_PROFILE *, struct _PM_PROFILE *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180021510`

## callees

- `0x1800025f0`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000d564`
- `0x18000dae8`
- `0x18000dcec`
- `0x18000dda4`
- `0x18000e43c`
- `0x18000e59c`
- `0x18000e948`
- `0x18000ec00`
- `0x18001d828`
- `0x18001dbcc`
- `0x180032f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e9f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e9f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb8b`

## pseudocode

```c
__int64 __fastcall PmpUpdateProfile(struct _GUID *a1, struct _PM_PROFILE *a2, struct _PM_PROFILE *a3, int a4)
{
  unsigned __int16 *v4; // r15
  unsigned int v9; // esi
  unsigned int v10; // ebx
  struct _PM_PCB_LIST *v11; // r14
  unsigned int KeyPcb; // eax
  struct _PM_PCB *v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // eax
  void *v16; // r8
  GUID *v17; // r13
  struct _PM_PCB **v18; // rax
  __int64 v19; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-48h] BYREF
  struct _PM_PCB_LIST *v23; // [rsp+40h] [rbp-40h] BYREF
  struct _PM_PCB *lpMem; // [rsp+48h] [rbp-38h] BYREF
  struct _PM_PCB *v25; // [rsp+50h] [rbp-30h] BYREF
  GUID *rguid; // [rsp+58h] [rbp-28h]
  GUID v27; // [rsp+60h] [rbp-20h] BYREF

  rguid = a1;
  v4 = 0;
  v23 = 0;
  v27 = 0;
  v22 = 0;
  v25 = 0;
  lpMem = 0;
  *(_DWORD *)Data = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 43, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  v9 = 2;
  if ( a1 && a4 != 2 )
    v9 = 0;
  EnterCriticalSection(&stru_180052D40);
  v10 = PmpReferencePcbList(a1, v9, &v23);
  if ( !v10 )
  {
    v11 = v23;
    KeyPcb = PmpFindKeyPcb(v23, (const unsigned __int16 *)a3 + 12, v9, &lpMem);
    v10 = KeyPcb;
    if ( KeyPcb )
    {
      if ( KeyPcb != 1168 || a4 != 5 )
        goto LABEL_33;
      PmpUuidCreate(&v27);
      v13 = 0;
    }
    else
    {
      v13 = lpMem;
      if ( *((struct _PM_PCB_LIST **)lpMem + 8) != v11 )
        goto LABEL_11;
      v14 = *((_QWORD *)lpMem + 2) - *(_QWORD *)a3;
      if ( !v14 )
        v14 = *((_QWORD *)lpMem + 3) - *((_QWORD *)a3 + 1);
      if ( v14 || *((_DWORD *)lpMem + 10) != *((_DWORD *)a3 + 4) )
      {
LABEL_11:
        v10 = 183;
        goto LABEL_33;
      }
      v27 = (GUID)*((_OWORD *)lpMem + 1);
    }
    v15 = LpGenerateProfileXml(a2, &v22);
    v4 = v22;
    v10 = v15;
    if ( !v15 )
    {
      v17 = rguid;
      v10 = StSaveProfile(rguid, &v27, v16, v22);
      if ( !v10 )
      {
        *(_DWORD *)Data = v9;
        v10 = StSaveProfileMetaData(v17, &v27, Data);
        if ( !v10 )
        {
          if ( v13 )
          {
            v10 = PmpInitializeProfilePcb(v13, v9, a2, 0, 0);
            if ( v10 )
              goto LABEL_33;
            goto LABEL_32;
          }
          v10 = PmpAllocateProfilePcb(v9, a2, 0, v11, &v25);
          if ( !v10 )
          {
            v13 = v25;
            v18 = (struct _PM_PCB **)((char *)v11 + 40);
            *((GUID *)v25 + 1) = v27;
            v19 = *((_QWORD *)v11 + 5);
            if ( *(struct _PM_PCB_LIST **)(v19 + 8) != (struct _PM_PCB_LIST *)((char *)v11 + 40) )
              __fastfail(3u);
            *(_QWORD *)v13 = v19;
            *((_QWORD *)v13 + 1) = v18;
            *(_QWORD *)(v19 + 8) = v13;
            *v18 = v13;
            v10 = PmpSavePcbList(v11);
            if ( !v10 )
            {
              if ( (*((_BYTE *)v11 + 16) & 0x10) != 0 )
                PmpInvalidateVisibilityInterfacePcbLists();
LABEL_32:
              *(_OWORD *)a2 = *((_OWORD *)v13 + 1);
              *((_DWORD *)a2 + 4) = *((_DWORD *)v13 + 10);
            }
          }
        }
      }
    }
  }
LABEL_33:
  LeaveCriticalSection(&stru_180052D40);
  if ( v4 )
    Dot3Free(v4);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 44, WPP_935883eb83d333df730e157613565e66_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000e948  mov     [rsp-38h+arg_18], rbx
0x18000e94d  push    rbp
0x18000e94e  push    rsi
0x18000e94f  push    rdi
0x18000e950  push    r12
0x18000e952  push    r13
0x18000e954  push    r14
0x18000e956  push    r15
0x18000e958  mov     rbp, rsp
0x18000e95b  sub     rsp, 80h
0x18000e962  mov     rax, cs:__security_cookie
0x18000e969  xor     rax, rsp
0x18000e96c  mov     [rbp+var_10], rax
0x18000e970  xorps   xmm0, xmm0
0x18000e973  mov     [rbp+rguid], rcx
0x18000e977  xor     r15d, r15d
0x18000e97a  mov     [rbp+var_40], 0
0x18000e982  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000e986  mov     [rbp+var_48], r15
0x18000e98a  mov     edi, r9d
0x18000e98d  mov     r13, r8
0x18000e990  mov     [rbp+var_30], 0
0x18000e998  mov     r12, rdx
0x18000e99b  mov     [rbp+lpMem], 0
0x18000e9a3  mov     rbx, rcx
0x18000e9a6  mov     dword ptr [rbp+Data], 0
0x18000e9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b4  lea     r14, WPP_GLOBAL_Control
0x18000e9bb  cmp     rcx, r14
0x18000e9be  jz      short loc_18000E9E0
0x18000e9c0  cmp     byte ptr [rcx+19h], 4
0x18000e9c4  jb      short loc_18000E9E0
0x18000e9c6  test    byte ptr [rcx+1Ch], 1
0x18000e9ca  jz      short loc_18000E9E0
0x18000e9cc  mov     rcx, [rcx+10h]
0x18000e9d0  lea     edx, [r15+2Bh]
0x18000e9d4  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000e9db  call    WPP_SF_
0x18000e9e0  mov     esi, 2
0x18000e9e5  test    rbx, rbx
0x18000e9e8  jz      short loc_18000E9F0
0x18000e9ea  cmp     edi, esi
0x18000e9ec  jz      short loc_18000E9F0
0x18000e9ee  xor     esi, esi
0x18000e9f0  lea     rcx, stru_180052D40; lpCriticalSection
0x18000e9f7  call    cs:__imp_EnterCriticalSection
0x18000e9fd  lea     r8, [rbp+var_40]; struct _PM_PCB_LIST **
0x18000ea01  mov     edx, esi; unsigned int
0x18000ea03  mov     rcx, rbx; struct _GUID *
0x18000ea06  call    ?PmpReferencePcbList@@YAKPEAU_GUID@@KPEAPEAU_PM_PCB_LIST@@@Z; PmpReferencePcbList(_GUID *,ulong,_PM_PCB_LIST * *)
0x18000ea0b  mov     ebx, eax
0x18000ea0d  test    eax, eax
0x18000ea0f  jnz     loc_18000EB84
0x18000ea15  mov     r14, [rbp+var_40]
0x18000ea19  lea     rdx, [r13+18h]; unsigned __int16 *
0x18000ea1d  mov     rcx, r14; struct _PM_PCB_LIST *
0x18000ea20  lea     r9, [rbp+lpMem]; struct _PM_PCB **
0x18000ea24  mov     r8d, esi; unsigned int
0x18000ea27  call    ?PmpFindKeyPcb@@YAKPEAU_PM_PCB_LIST@@PEBGKPEAPEAU_PM_PCB@@@Z; PmpFindKeyPcb(_PM_PCB_LIST *,ushort const *,ulong,_PM_PCB * *)
0x18000ea2c  mov     ebx, eax
0x18000ea2e  test    eax, eax
0x18000ea30  jnz     short loc_18000EA71
0x18000ea32  mov     rdi, [rbp+lpMem]
0x18000ea36  cmp     [rdi+40h], r14
0x18000ea3a  jz      short loc_18000EA46
0x18000ea3c  mov     ebx, 0B7h
0x18000ea41  jmp     loc_18000EB7D
0x18000ea46  mov     rax, [rdi+10h]
0x18000ea4a  sub     rax, [r13+0]
0x18000ea4e  jnz     short loc_18000EA58
0x18000ea50  mov     rax, [rdi+18h]
0x18000ea54  sub     rax, [r13+8]
0x18000ea58  test    rax, rax
0x18000ea5b  jnz     short loc_18000EA3C
0x18000ea5d  mov     eax, [r13+10h]
0x18000ea61  cmp     [rdi+28h], eax
0x18000ea64  jnz     short loc_18000EA3C
0x18000ea66  movups  xmm0, xmmword ptr [rdi+10h]
0x18000ea6a  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000ea6f  jmp     short loc_18000EA90
0x18000ea71  cmp     eax, 490h
0x18000ea76  jnz     loc_18000EB7D
0x18000ea7c  cmp     edi, 5
0x18000ea7f  jnz     loc_18000EB7D
0x18000ea85  lea     rcx, [rbp+var_20]; struct _GUID *
0x18000ea89  call    ?PmpUuidCreate@@YAKPEAU_GUID@@@Z; PmpUuidCreate(_GUID *)
0x18000ea8e  xor     edi, edi
0x18000ea90  lea     rdx, [rbp+var_48]
0x18000ea94  mov     rcx, r12
0x18000ea97  call    LpGenerateProfileXml
0x18000ea9c  mov     r15, [rbp+var_48]
0x18000eaa0  mov     ebx, eax
0x18000eaa2  test    eax, eax
0x18000eaa4  jnz     loc_18000EB7D
0x18000eaaa  mov     r13, [rbp+rguid]
0x18000eaae  lea     rdx, [rbp+var_20]; GUID *
0x18000eab2  mov     rcx, r13; rguid
0x18000eab5  mov     r9, r15; unsigned __int16 *
0x18000eab8  call    ?StSaveProfile@@YAKPEAU_GUID@@0PEAXPEBG@Z; StSaveProfile(_GUID *,_GUID *,void *,ushort const *)
0x18000eabd  mov     ebx, eax
0x18000eabf  test    eax, eax
0x18000eac1  jnz     loc_18000EB7D
0x18000eac7  lea     r8, [rbp+Data]; lpData
0x18000eacb  mov     dword ptr [rbp+Data], esi
0x18000eace  lea     rdx, [rbp+var_20]; GUID *
0x18000ead2  mov     rcx, r13; rguid
0x18000ead5  call    ?StSaveProfileMetaData@@YAKPEAU_GUID@@0PEAU_ST_PROFILE_METADATA@@@Z; StSaveProfileMetaData(_GUID *,_GUID *,_ST_PROFILE_METADATA *)
0x18000eada  mov     ebx, eax
0x18000eadc  test    eax, eax
0x18000eade  jnz     loc_18000EB7D
0x18000eae4  test    rdi, rdi
0x18000eae7  jz      short loc_18000EB05
0x18000eae9  xor     r9d, r9d; unsigned __int16 *
0x18000eaec  mov     dword ptr [rsp+80h+var_60], eax; int
0x18000eaf0  mov     r8, r12; struct _PM_PROFILE *
0x18000eaf3  mov     edx, esi; unsigned int
0x18000eaf5  mov     rcx, rdi; lpMem
0x18000eaf8  call    ?PmpInitializeProfilePcb@@YAKPEAU_PM_PCB@@KPEAU_PM_PROFILE@@PEBGH@Z; PmpInitializeProfilePcb(_PM_PCB *,ulong,_PM_PROFILE *,ushort const *,int)
0x18000eafd  mov     ebx, eax
0x18000eaff  test    eax, eax
0x18000eb01  jnz     short loc_18000EB7D
0x18000eb03  jmp     short loc_18000EB6B
0x18000eb05  lea     rax, [rbp+var_30]
0x18000eb09  mov     r9, r14; struct _PM_PCB_LIST *
0x18000eb0c  xor     r8d, r8d; unsigned __int16 *
0x18000eb0f  mov     [rsp+80h+var_60], rax; struct _PM_PCB **
0x18000eb14  mov     rdx, r12; struct _PM_PROFILE *
0x18000eb17  mov     ecx, esi; unsigned int
0x18000eb19  call    ?PmpAllocateProfilePcb@@YAKKPEAU_PM_PROFILE@@PEBGPEAU_PM_PCB_LIST@@PEAPEAU_PM_PCB@@@Z; PmpAllocateProfilePcb(ulong,_PM_PROFILE *,ushort const *,_PM_PCB_LIST *,_PM_PCB * *)
0x18000eb1e  mov     ebx, eax
0x18000eb20  test    eax, eax
0x18000eb22  jnz     short loc_18000EB7D
0x18000eb24  mov     rdi, [rbp+var_30]
0x18000eb28  lea     rax, [r14+28h]
0x18000eb2c  movups  xmm0, xmmword ptr [rbp+var_20.Data1]
0x18000eb30  movdqu  xmmword ptr [rdi+10h], xmm0
0x18000eb35  mov     rcx, [rax]
0x18000eb38  cmp     [rcx+8], rax
0x18000eb3c  jz      short loc_18000EB43
0x18000eb3e  lea     ecx, [rbx+3]
0x18000eb41  int     29h; Win8: RtlFailFast(ecx)
0x18000eb43  mov     [rdi], rcx
0x18000eb46  mov     [rdi+8], rax
0x18000eb4a  mov     [rcx+8], rdi
0x18000eb4e  mov     rcx, r14; struct _PM_PCB_LIST *
0x18000eb51  mov     [rax], rdi
0x18000eb54  call    ?PmpSavePcbList@@YAKPEAU_PM_PCB_LIST@@@Z; PmpSavePcbList(_PM_PCB_LIST *)
0x18000eb59  mov     ebx, eax
0x18000eb5b  test    eax, eax
0x18000eb5d  jnz     short loc_18000EB7D
0x18000eb5f  test    byte ptr [r14+10h], 10h
0x18000eb64  jz      short loc_18000EB6B
0x18000eb66  call    ?PmpInvalidateVisibilityInterfacePcbLists@@YAXXZ; PmpInvalidateVisibilityInterfacePcbLists(void)
0x18000eb6b  movups  xmm0, xmmword ptr [rdi+10h]
0x18000eb6f  movdqu  xmmword ptr [r12], xmm0
0x18000eb75  mov     eax, [rdi+28h]
0x18000eb78  mov     [r12+10h], eax
0x18000eb7d  lea     r14, WPP_GLOBAL_Control
0x18000eb84  lea     rcx, stru_180052D40; lpCriticalSection
0x18000eb8b  call    cs:__imp_LeaveCriticalSection
0x18000eb91  test    r15, r15
0x18000eb94  jz      short loc_18000EB9E
0x18000eb96  mov     rcx, r15; lpMem
0x18000eb99  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18000eb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eba5  cmp     rcx, r14
0x18000eba8  jz      short loc_18000EBCE
0x18000ebaa  cmp     byte ptr [rcx+19h], 4
0x18000ebae  jb      short loc_18000EBCE
0x18000ebb0  test    byte ptr [rcx+1Ch], 1
0x18000ebb4  jz      short loc_18000EBCE
0x18000ebb6  mov     rcx, [rcx+10h]
0x18000ebba  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ebc1  mov     edx, 2Ch ; ','
0x18000ebc6  mov     r9d, ebx
0x18000ebc9  call    WPP_SF_d
0x18000ebce  mov     eax, ebx
0x18000ebd0  mov     rcx, [rbp+var_10]
0x18000ebd4  xor     rcx, rsp; StackCookie
0x18000ebd7  call    __security_check_cookie
0x18000ebdc  mov     rbx, [rsp+80h+arg_18]
0x18000ebe4  add     rsp, 80h
0x18000ebeb  pop     r15
0x18000ebed  pop     r14
0x18000ebef  pop     r13
0x18000ebf1  pop     r12
0x18000ebf3  pop     rdi
0x18000ebf4  pop     rsi
0x18000ebf5  pop     rbp
0x18000ebf6  retn
```
