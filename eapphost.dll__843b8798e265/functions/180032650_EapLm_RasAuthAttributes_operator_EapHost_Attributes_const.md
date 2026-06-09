# EapLm::RasAuthAttributes::operator=(EapHost::Attributes const &)

- ea: `0x180032650`
- end: `0x180032786`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@AEBVAttributes@EapHost@@@Z`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180013090`
- `0x180015160`

## callees

- `0x18000a4d4`
- `0x18001e7c0`
- `0x18001eb50`
- `0x18001ebb8`
- `0x18002fe84`
- `0x180032650`
- `0x1800329c0`
- `0x1800329ec`
- `0x180032bb4`
- `0x180032c48`
- `0x180032cd0`

## string_xrefs

- `0x180032688`: `RasAuthAttributeCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
EapLm::RasAuthAttributes *__fastcall EapLm::RasAuthAttributes::operator=(
        EapLm::RasAuthAttributes *a1,
        const struct _EAP_ATTRIBUTES *a2)
{
  unsigned __int64 v3; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v4; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v5; // rsi
  int v6; // ebp
  EapLm *v7; // rdi
  EapHost::Peer::Host *v8; // rcx
  __int64 v9; // rdx
  unsigned __int8 *v10; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v11; // r8
  enum _RAS_AUTH_ATTRIBUTE_TYPE_ v12; // r9d
  int v13; // r10d
  unsigned int v14; // eax
  void *v16[2]; // [rsp+30h] [rbp-58h] BYREF
  EapLm *v17; // [rsp+40h] [rbp-48h]

  if ( !a2->dwNumberOfAttributes )
  {
    EapLm::RasAuthAttributes::Destroy(a1);
    return a1;
  }
  EapHost::AutoAttributes::AutoAttributes((EapHost::AutoAttributes *)v16, a2);
  v5 = EapLm::RasAuthAttributeCreate(v17, v3);
  if ( !v5 )
    LowMemoryError::Throw(L"RasAuthAttributeCreate");
  v6 = 0;
  v7 = 0;
  v8 = WPP_GLOBAL_Control;
  while ( v7 < v17 )
  {
    if ( *((_DWORD *)v16[0] + 4 * (_QWORD)v7 + 1) && (v9 = *((_QWORD *)v16[0] + 2 * (_QWORD)v7 + 1)) != 0 )
    {
      if ( EapLm::IsPointerValue(
             (EapLm *)*((unsigned int *)v16[0] + 4 * (_QWORD)v7),
             (enum _RAS_AUTH_ATTRIBUTE_TYPE_)v9) )
      {
        v14 = EapLm::RasAuthAttributeInsert(v7, (unsigned __int64)v5, v11, v12, v13, (unsigned int)v10, v16[0]);
      }
      else
      {
        v14 = EapLm::RasAuthAttributeInsert(v7, (unsigned __int64)v5, v11, v12, v13, *v10, v16[0]);
      }
      v6 = v14;
    }
    else
    {
      v4 = (struct _RAS_AUTH_ATTRIBUTE *)&WPP_GLOBAL_Control;
      if ( v8 == (EapHost::Peer::Host *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
        goto LABEL_18;
      WPP_SF_dd(
        *((_QWORD *)v8 + 2),
        10,
        WPP_95f9c60226ea37d25f480d31695c5346_Traceguids,
        *((unsigned int *)v16[0] + 4 * (_QWORD)v7),
        *((_DWORD *)v16[0] + 4 * (_QWORD)v7 + 1));
    }
    if ( v6 )
    {
      EapLm::RasAuthAttributeDestroy(v5, v4);
      EapHost::EapException::Throw(L"RasAuthAttributeInsert", &qword_18003D520, v6);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_18:
    v7 = (EapLm *)((char *)v7 + 1);
  }
  if ( *(_QWORD *)a1 )
    EapLm::RasAuthAttributeDestroy(*(HLOCAL *)a1, v4);
  *(_QWORD *)a1 = v5;
  EapHost::AutoAttributes::~AutoAttributes((EapHost::AutoAttributes *)v16);
  return a1;
}

```

## disassembly

```asm
0x180032650  push    rbx
0x180032652  push    rbp
0x180032653  push    rsi
0x180032654  push    rdi
0x180032655  sub     rsp, 68h
0x180032659  mov     rbx, rcx
0x18003265c  cmp     dword ptr [rdx], 0
0x18003265f  jnz     short loc_18003266B
0x180032661  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x180032666  jmp     loc_180032779
0x18003266b  lea     rcx, [rsp+88h+var_58]; this
0x180032670  call    ??0AutoAttributes@EapHost@@QEAA@AEBU_EAP_ATTRIBUTES@@@Z; EapHost::AutoAttributes::AutoAttributes(_EAP_ATTRIBUTES const &)
0x180032675  nop
0x180032676  mov     rcx, [rsp+88h+var_48]; this
0x18003267b  call    ?RasAuthAttributeCreate@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@_K@Z; EapLm::RasAuthAttributeCreate(unsigned __int64)
0x180032680  mov     rsi, rax
0x180032683  test    rax, rax
0x180032686  jnz     short loc_180032695
0x180032688  lea     rcx, aRasauthattribu_2; "RasAuthAttributeCreate"
0x18003268f  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180032695  xor     ebp, ebp
0x180032697  xor     edi, edi
0x180032699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326a0  cmp     rdi, [rsp+88h+var_48]
0x1800326a5  jnb     loc_18003275F
0x1800326ab  mov     r9, rdi
0x1800326ae  add     r9, r9
0x1800326b1  mov     rax, [rsp+88h+var_58]
0x1800326b6  mov     r10d, [rax+r9*8+4]
0x1800326bb  test    r10d, r10d
0x1800326be  jz      short loc_1800326FD
0x1800326c0  mov     rdx, [rax+r9*8+8]; enum _RAS_AUTH_ATTRIBUTE_TYPE_
0x1800326c5  test    rdx, rdx
0x1800326c8  jz      short loc_1800326FD
0x1800326ca  mov     r8d, [rax+r9*8]
0x1800326ce  mov     ecx, r8d; this
0x1800326d1  call    ?IsPointerValue@EapLm@@YA_NW4_RAS_AUTH_ATTRIBUTE_TYPE_@@@Z; EapLm::IsPointerValue(_RAS_AUTH_ATTRIBUTE_TYPE_)
0x1800326d6  mov     rcx, rdi; this
0x1800326d9  test    al, al
0x1800326db  jz      short loc_1800326E4
0x1800326dd  mov     qword ptr [rsp+88h+var_60], rdx
0x1800326e2  jmp     short loc_1800326EC
0x1800326e4  movzx   eax, byte ptr [rdx]
0x1800326e7  mov     qword ptr [rsp+88h+var_60], rax; unsigned int
0x1800326ec  mov     [rsp+88h+var_68], r10d; int
0x1800326f1  mov     rdx, rsi; unsigned __int64
0x1800326f4  call    ?RasAuthAttributeInsert@EapLm@@YAK_KPEAU_RAS_AUTH_ATTRIBUTE@@W4_RAS_AUTH_ATTRIBUTE_TYPE_@@HKPEAX@Z; EapLm::RasAuthAttributeInsert(unsigned __int64,_RAS_AUTH_ATTRIBUTE *,_RAS_AUTH_ATTRIBUTE_TYPE_,int,ulong,void *)
0x1800326f9  mov     ebp, eax
0x1800326fb  jmp     short loc_18003272D
0x1800326fd  lea     rdx, WPP_GLOBAL_Control
0x180032704  cmp     rcx, rdx
0x180032707  jz      short loc_180032738
0x180032709  test    byte ptr [rcx+1Ch], 1
0x18003270d  jz      short loc_180032738
0x18003270f  mov     edx, 0Ah
0x180032714  mov     [rsp+88h+var_68], r10d
0x180032719  mov     r9d, [rax+r9*8]
0x18003271d  lea     r8, WPP_95f9c60226ea37d25f480d31695c5346_Traceguids
0x180032724  mov     rcx, [rcx+10h]
0x180032728  call    WPP_SF_dd
0x18003272d  test    ebp, ebp
0x18003272f  jnz     short loc_180032740
0x180032731  mov     rcx, cs:WPP_GLOBAL_Control
0x180032738  inc     rdi
0x18003273b  jmp     loc_1800326A0
0x180032740  mov     rcx, rsi; hMem
0x180032743  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x180032748  mov     r8d, ebp; int
0x18003274b  lea     rdx, qword_18003D520; wchar_t *
0x180032752  lea     rcx, aRasauthattribu; "RasAuthAttributeInsert"
0x180032759  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18003275f  mov     rcx, [rbx]; hMem
0x180032762  test    rcx, rcx
0x180032765  jz      short loc_18003276C
0x180032767  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x18003276c  mov     [rbx], rsi
0x18003276f  lea     rcx, [rsp+88h+var_58]; this
0x180032774  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x180032779  mov     rax, rbx
0x18003277c  add     rsp, 68h
0x180032780  pop     rdi
0x180032781  pop     rsi
0x180032782  pop     rbp
0x180032783  pop     rbx
0x180032784  retn
```
