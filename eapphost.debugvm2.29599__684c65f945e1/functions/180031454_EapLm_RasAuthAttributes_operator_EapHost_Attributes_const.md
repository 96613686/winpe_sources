# EapLm::RasAuthAttributes::operator=(EapHost::Attributes const &)

- ea: `0x180031454`
- end: `0x180031589`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@AEBVAttributes@EapHost@@@Z`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180012900`
- `0x180014940`

## callees

- `0x18000a050`
- `0x18001dcbc`
- `0x18001e038`
- `0x18001e0a0`
- `0x18002ed84`
- `0x180031454`
- `0x1800317bc`
- `0x1800317e8`
- `0x1800319ac`
- `0x180031a38`
- `0x180031ab4`

## string_xrefs

- `0x18003148c`: `RasAuthAttributeCreate`

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
      EapHost::EapException::Throw(L"RasAuthAttributeInsert", &qword_18003C520, v6);
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
0x180031454  push    rbx
0x180031456  push    rbp
0x180031457  push    rsi
0x180031458  push    rdi
0x180031459  sub     rsp, 68h
0x18003145d  mov     rbx, rcx
0x180031460  cmp     dword ptr [rdx], 0
0x180031463  jnz     short loc_18003146F
0x180031465  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x18003146a  jmp     loc_18003157D
0x18003146f  lea     rcx, [rsp+88h+var_58]; this
0x180031474  call    ??0AutoAttributes@EapHost@@QEAA@AEBU_EAP_ATTRIBUTES@@@Z; EapHost::AutoAttributes::AutoAttributes(_EAP_ATTRIBUTES const &)
0x180031479  nop
0x18003147a  mov     rcx, [rsp+88h+var_48]; this
0x18003147f  call    ?RasAuthAttributeCreate@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@_K@Z; EapLm::RasAuthAttributeCreate(unsigned __int64)
0x180031484  mov     rsi, rax
0x180031487  test    rax, rax
0x18003148a  jnz     short loc_180031499
0x18003148c  lea     rcx, aRasauthattribu_2; "RasAuthAttributeCreate"
0x180031493  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180031499  xor     ebp, ebp
0x18003149b  xor     edi, edi
0x18003149d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314a4  cmp     rdi, [rsp+88h+var_48]
0x1800314a9  jnb     loc_180031563
0x1800314af  mov     r9, rdi
0x1800314b2  add     r9, r9
0x1800314b5  mov     rax, [rsp+88h+var_58]
0x1800314ba  mov     r10d, [rax+r9*8+4]
0x1800314bf  test    r10d, r10d
0x1800314c2  jz      short loc_180031501
0x1800314c4  mov     rdx, [rax+r9*8+8]; enum _RAS_AUTH_ATTRIBUTE_TYPE_
0x1800314c9  test    rdx, rdx
0x1800314cc  jz      short loc_180031501
0x1800314ce  mov     r8d, [rax+r9*8]
0x1800314d2  mov     ecx, r8d; this
0x1800314d5  call    ?IsPointerValue@EapLm@@YA_NW4_RAS_AUTH_ATTRIBUTE_TYPE_@@@Z; EapLm::IsPointerValue(_RAS_AUTH_ATTRIBUTE_TYPE_)
0x1800314da  mov     rcx, rdi; this
0x1800314dd  test    al, al
0x1800314df  jz      short loc_1800314E8
0x1800314e1  mov     qword ptr [rsp+88h+var_60], rdx
0x1800314e6  jmp     short loc_1800314F0
0x1800314e8  movzx   eax, byte ptr [rdx]
0x1800314eb  mov     qword ptr [rsp+88h+var_60], rax; unsigned int
0x1800314f0  mov     [rsp+88h+var_68], r10d; int
0x1800314f5  mov     rdx, rsi; unsigned __int64
0x1800314f8  call    ?RasAuthAttributeInsert@EapLm@@YAK_KPEAU_RAS_AUTH_ATTRIBUTE@@W4_RAS_AUTH_ATTRIBUTE_TYPE_@@HKPEAX@Z; EapLm::RasAuthAttributeInsert(unsigned __int64,_RAS_AUTH_ATTRIBUTE *,_RAS_AUTH_ATTRIBUTE_TYPE_,int,ulong,void *)
0x1800314fd  mov     ebp, eax
0x1800314ff  jmp     short loc_180031531
0x180031501  lea     rdx, WPP_GLOBAL_Control
0x180031508  cmp     rcx, rdx
0x18003150b  jz      short loc_18003153C
0x18003150d  test    byte ptr [rcx+1Ch], 1
0x180031511  jz      short loc_18003153C
0x180031513  mov     edx, 0Ah
0x180031518  mov     [rsp+88h+var_68], r10d
0x18003151d  mov     r9d, [rax+r9*8]
0x180031521  lea     r8, WPP_95f9c60226ea37d25f480d31695c5346_Traceguids
0x180031528  mov     rcx, [rcx+10h]
0x18003152c  call    WPP_SF_dd
0x180031531  test    ebp, ebp
0x180031533  jnz     short loc_180031544
0x180031535  mov     rcx, cs:WPP_GLOBAL_Control
0x18003153c  inc     rdi
0x18003153f  jmp     loc_1800314A4
0x180031544  mov     rcx, rsi; hMem
0x180031547  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x18003154c  mov     r8d, ebp; int
0x18003154f  lea     rdx, qword_18003C520; wchar_t *
0x180031556  lea     rcx, aRasauthattribu; "RasAuthAttributeInsert"
0x18003155d  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180031563  mov     rcx, [rbx]; hMem
0x180031566  test    rcx, rcx
0x180031569  jz      short loc_180031570
0x18003156b  call    ?RasAuthAttributeDestroy@EapLm@@YAXPEAU_RAS_AUTH_ATTRIBUTE@@@Z; EapLm::RasAuthAttributeDestroy(_RAS_AUTH_ATTRIBUTE *)
0x180031570  mov     [rbx], rsi
0x180031573  lea     rcx, [rsp+88h+var_58]; this
0x180031578  call    ??1AutoAttributes@EapHost@@QEAA@XZ; EapHost::AutoAttributes::~AutoAttributes(void)
0x18003157d  mov     rax, rbx
0x180031580  add     rsp, 68h
0x180031584  pop     rdi
0x180031585  pop     rsi
0x180031586  pop     rbp
0x180031587  pop     rbx
0x180031588  retn
```
