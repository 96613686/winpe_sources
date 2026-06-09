# DifNtOpenEnlistmentWrapper

- ea: `0x14065bdc0`
- end: `0x14065bf4d`
- name: `DifNtOpenEnlistmentWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065bdc0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenEnlistment` at `0x14065bec1`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenEnlistment` at `0x14065bec1`

## pseudocode

```c
__int64 __fastcall DifNtOpenEnlistmentWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        void *a3,
        GUID *a4,
        OBJECT_ATTRIBUTES *ObjectAttributes)
{
  __int64 APIThunkContextById; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r14
  __int64 v12; // rcx
  BOOLEAN v13; // si
  _QWORD *i; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  BOOLEAN v17; // di
  _QWORD *j; // rbx
  __int128 v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+40h] [rbp-38h]
  __int128 v22; // [rsp+50h] [rbp-28h]
  __int64 v23; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v23 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(539);
  v11 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v12 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v12 & 0x18) != 0 )
    {
      *(_QWORD *)&v20 = retaddr;
    }
    else if ( (v12 & 4) != 0 )
    {
      *(_QWORD *)&v20 = DifGetReturnAddressForWrappers(v12, v9, v10);
    }
    *((_QWORD *)&v22 + 1) = a1;
    *((_QWORD *)&v20 + 1) = ObjectAttributes;
    LODWORD(v22) = a2;
    *((_QWORD *)&v21 + 1) = a3;
    *(_QWORD *)&v21 = a4;
    if ( !VfDifRunningWithoutReboot && (v13 = 0, (VfOptionFlags & 0x800) == 0)
      || (v13 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v11 + 32); i != (_QWORD *)(v11 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v9, v10);
      }
      if ( v13 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v23) = NtOpenEnlistment(a1, a2, a3, a4, ObjectAttributes);
  if ( v11 )
  {
    if ( !VfDifRunningWithoutReboot && (v17 = 0, (VfOptionFlags & 0x800) == 0)
      || (v17 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v11 + 48); j != (_QWORD *)(v11 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v15, v16);
      }
      if ( v17 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14065bdc0  mov     [rsp-40h+EnlistmentHandle], rcx
0x14065bdc5  push    rbp
0x14065bdc6  push    rbx
0x14065bdc7  push    rsi
0x14065bdc8  push    rdi
0x14065bdc9  push    r12
0x14065bdcb  push    r13
0x14065bdcd  push    r14
0x14065bdcf  push    r15
0x14065bdd1  mov     rbp, rsp
0x14065bdd4  sub     rsp, 78h
0x14065bdd8  xorps   xmm0, xmm0
0x14065bddb  xor     eax, eax
0x14065bddd  mov     ecx, 21Bh
0x14065bde2  mov     [rbp+var_18], rax
0x14065bde6  movups  [rbp+var_48], xmm0
0x14065bdea  mov     r15, r9
0x14065bded  mov     r12, r8
0x14065bdf0  movups  [rbp+var_38], xmm0
0x14065bdf4  mov     r13d, edx
0x14065bdf7  movups  [rbp+var_28], xmm0
0x14065bdfb  call    DifGetAPIThunkContextById
0x14065be00  mov     r14, rax
0x14065be03  test    rax, rax
0x14065be06  jz      loc_14065BEAB
0x14065be0c  mov     ecx, [rax+0Ch]
0x14065be0f  test    cl, 18h
0x14065be12  jz      short loc_14065BE1E
0x14065be14  mov     rcx, [rbp+40h]
0x14065be18  mov     qword ptr [rbp+var_48], rcx
0x14065be1c  jmp     short loc_14065BE2C
0x14065be1e  test    cl, 4
0x14065be21  jz      short loc_14065BE2C
0x14065be23  call    DifGetReturnAddressForWrappers
0x14065be28  mov     qword ptr [rbp+var_48], rax
0x14065be2c  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065be33  mov     rax, [rbp+EnlistmentHandle]
0x14065be37  mov     qword ptr [rbp+var_28+8], rax
0x14065be3b  mov     rax, [rbp+arg_20]
0x14065be3f  mov     qword ptr [rbp+var_48+8], rax
0x14065be43  mov     dword ptr [rbp+var_28], r13d
0x14065be47  mov     qword ptr [rbp+var_38+8], r12
0x14065be4b  mov     qword ptr [rbp+var_38], r15
0x14065be4f  jnz     short loc_14065BE60
0x14065be51  xor     sil, sil
0x14065be54  test    cs:VfOptionFlags, 800h
0x14065be5e  jz      short loc_14065BE73
0x14065be60  lea     rcx, DifRebootlessRundown; RunRef
0x14065be67  call    ExAcquireRundownProtection_0
0x14065be6c  mov     sil, al
0x14065be6f  test    al, al
0x14065be71  jz      short loc_14065BEAB
0x14065be73  lea     rdi, [r14+20h]
0x14065be77  mov     rbx, [rdi]
0x14065be7a  jmp     short loc_14065BE95
0x14065be7c  lea     rax, [rbx-10h]
0x14065be80  test    rax, rax
0x14065be83  jz      short loc_14065BE92
0x14065be85  mov     rax, [rax+8]
0x14065be89  lea     rcx, [rbp+var_48]
0x14065be8d  call    _guard_dispatch_icall_no_overrides
0x14065be92  mov     rbx, [rbx]
0x14065be95  cmp     rbx, rdi
0x14065be98  jnz     short loc_14065BE7C
0x14065be9a  test    sil, sil
0x14065be9d  jz      short loc_14065BEAB
0x14065be9f  lea     rcx, DifRebootlessRundown; RunRef
0x14065bea6  call    ExReleaseRundownProtection_0
0x14065beab  mov     rax, [rbp+arg_20]
0x14065beaf  mov     r9, r15; EnlistmentGuid
0x14065beb2  mov     rcx, [rbp+EnlistmentHandle]; EnlistmentHandle
0x14065beb6  mov     r8, r12; ResourceManagerHandle
0x14065beb9  mov     edx, r13d; DesiredAccess
0x14065bebc  mov     [rsp+78h+ObjectAttributes], rax; ObjectAttributes
0x14065bec1  call    cs:__imp_NtOpenEnlistment
0x14065bec8  nop     dword ptr [rax+rax+00h]
0x14065becd  mov     dword ptr [rbp+var_18], eax
0x14065bed0  test    r14, r14
0x14065bed3  jz      short loc_14065BF38
0x14065bed5  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065bedc  jnz     short loc_14065BEED
0x14065bede  xor     dil, dil
0x14065bee1  test    cs:VfOptionFlags, 800h
0x14065beeb  jz      short loc_14065BF00
0x14065beed  lea     rcx, DifRebootlessRundown; RunRef
0x14065bef4  call    ExAcquireRundownProtection_0
0x14065bef9  mov     dil, al
0x14065befc  test    al, al
0x14065befe  jz      short loc_14065BF38
0x14065bf00  lea     rsi, [r14+30h]
0x14065bf04  mov     rbx, [rsi]
0x14065bf07  jmp     short loc_14065BF22
0x14065bf09  lea     rax, [rbx-10h]
0x14065bf0d  test    rax, rax
0x14065bf10  jz      short loc_14065BF1F
0x14065bf12  mov     rax, [rax+8]
0x14065bf16  lea     rcx, [rbp+var_48]
0x14065bf1a  call    _guard_dispatch_icall_no_overrides
0x14065bf1f  mov     rbx, [rbx]
0x14065bf22  cmp     rbx, rsi
0x14065bf25  jnz     short loc_14065BF09
0x14065bf27  test    dil, dil
0x14065bf2a  jz      short loc_14065BF38
0x14065bf2c  lea     rcx, DifRebootlessRundown; RunRef
0x14065bf33  call    ExReleaseRundownProtection_0
0x14065bf38  mov     eax, dword ptr [rbp+var_18]
0x14065bf3b  add     rsp, 78h
0x14065bf3f  pop     r15
0x14065bf41  pop     r14
0x14065bf43  pop     r13
0x14065bf45  pop     r12
0x14065bf47  pop     rdi
0x14065bf48  pop     rsi
0x14065bf49  pop     rbx
0x14065bf4a  pop     rbp
0x14065bf4b  retn
```
