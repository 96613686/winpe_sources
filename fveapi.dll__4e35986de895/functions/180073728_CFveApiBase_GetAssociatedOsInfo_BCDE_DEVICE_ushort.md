# CFveApiBase::GetAssociatedOsInfo(_BCDE_DEVICE * *,ushort * *)

- ea: `0x180073728`
- end: `0x180073871`
- name: `?GetAssociatedOsInfo@CFveApiBase@@SAJPEAPEAU_BCDE_DEVICE@@PEAPEAG@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct _BCDE_DEVICE **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ce438`

## callees

- `0x18000ba30`
- `0x180018b10`
- `0x180073728`
- `0x18009ba80`
- `0x18009befc`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x180073836`
- `bcd!BcdCloseObject` at `0x180122b2e`
- `bcd!BcdCloseObject` at `0x180073836`
- `bcd!BcdCloseObject` at `0x180122b2e`
- `bcd!BcdOpenObject` at `0x1800737bf`
- `bcd!BcdOpenObject` at `0x1800737bf`
- `bcd!BcdCloseStore` at `0x180073847`
- `bcd!BcdCloseStore` at `0x180122b3e`
- `bcd!BcdCloseStore` at `0x180073847`
- `bcd!BcdCloseStore` at `0x180122b3e`
- `bcd!BcdOpenSystemStore` at `0x18007377a`
- `bcd!BcdOpenSystemStore` at `0x18007377a`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetAssociatedOsInfo(struct _BCDE_DEVICE **a1, unsigned __int16 **a2)
{
  int v3; // eax
  __int64 v4; // rdx
  int AssociatedOs; // ebx
  int v6; // eax
  void *v7; // rcx
  void *lpMem; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+38h] [rbp-40h]
  void *v12; // [rsp+40h] [rbp-38h] BYREF
  void *v13; // [rsp+48h] [rbp-30h] BYREF
  struct _GUID v14; // [rsp+50h] [rbp-28h] BYREF

  v14 = 0;
  v12 = 0;
  v13 = 0;
  lpMem = 0;
  v10 = 0;
  v11 = 0;
  v3 = BcdOpenSystemStore(&v12, a2);
  AssociatedOs = FromNtStatus(v3);
  if ( AssociatedOs >= 0 )
  {
    AssociatedOs = CFveApiBase::GetAssociatedOs(v12, &v14);
    if ( AssociatedOs >= 0 )
    {
      v6 = BcdOpenObject(v12, &v14, &v13);
      AssociatedOs = FromNtStatus(v6);
      if ( AssociatedOs >= 0 )
      {
        AssociatedOs = CFveApiBase::GetBcdElementData(v13, 0x11000001u, &lpMem, &v10);
        if ( AssociatedOs >= 0 )
        {
          *a1 = (struct _BCDE_DEVICE *)lpMem;
          lpMem = 0;
        }
      }
    }
  }
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  v7 = v12;
  if ( v12 )
  {
    if ( v13 )
    {
      BcdCloseObject(v13);
      v7 = v12;
    }
    BcdCloseStore(v7, v4);
  }
  return (unsigned int)AssociatedOs;
}

```

## disassembly

```asm
0x180073728  mov     r11, rsp
0x18007372b  mov     [r11+10h], rbx
0x18007372f  push    rdi
0x180073730  sub     rsp, 70h
0x180073734  mov     rax, cs:__security_cookie
0x18007373b  xor     rax, rsp
0x18007373e  mov     [rsp+78h+var_18], rax
0x180073743  mov     rdi, rcx
0x180073746  xorps   xmm0, xmm0
0x180073749  movups  xmmword ptr [rsp+78h+var_28.Data1], xmm0
0x18007374e  mov     qword ptr [r11-38h], 0
0x180073756  mov     qword ptr [r11-30h], 0
0x18007375e  mov     qword ptr [r11-50h], 0
0x180073766  mov     [rsp+78h+var_48], 0
0x18007376e  mov     qword ptr [r11-40h], 0
0x180073776  lea     rcx, [r11-38h]
0x18007377a  call    cs:__imp_BcdOpenSystemStore
0x180073781  nop     dword ptr [rax+rax+00h]
0x180073786  mov     ecx, eax; int
0x180073788  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18007378d  mov     ebx, eax
0x18007378f  mov     [rsp+78h+var_58], eax
0x180073793  test    eax, eax
0x180073795  js      short loc_180073810
0x180073797  lea     rdx, [rsp+78h+var_28]; struct _GUID *
0x18007379c  mov     rcx, [rsp+78h+var_38]; void *
0x1800737a1  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x1800737a6  mov     ebx, eax
0x1800737a8  mov     [rsp+78h+var_58], eax
0x1800737ac  test    eax, eax
0x1800737ae  js      short loc_180073810
0x1800737b0  lea     r8, [rsp+78h+var_30]
0x1800737b5  lea     rdx, [rsp+78h+var_28]
0x1800737ba  mov     rcx, [rsp+78h+var_38]
0x1800737bf  call    cs:__imp_BcdOpenObject
0x1800737c6  nop     dword ptr [rax+rax+00h]
0x1800737cb  mov     ecx, eax; int
0x1800737cd  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800737d2  mov     ebx, eax
0x1800737d4  mov     [rsp+78h+var_58], eax
0x1800737d8  test    eax, eax
0x1800737da  js      short loc_180073810
0x1800737dc  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800737e1  lea     r8, [rsp+78h+lpMem]; void **
0x1800737e6  mov     edx, 11000001h; unsigned int
0x1800737eb  mov     rcx, [rsp+78h+var_30]; void *
0x1800737f0  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800737f5  mov     ebx, eax
0x1800737f7  mov     [rsp+78h+var_58], eax
0x1800737fb  test    eax, eax
0x1800737fd  js      short loc_180073810
0x1800737ff  mov     rax, [rsp+78h+lpMem]
0x180073804  mov     [rdi], rax
0x180073807  mov     [rsp+78h+lpMem], 0
0x180073810  mov     rcx, [rsp+78h+lpMem]; lpMem
0x180073815  test    rcx, rcx
0x180073818  jz      short loc_18007381F
0x18007381a  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18007381f  mov     rcx, [rsp+78h+var_38]
0x180073824  test    rcx, rcx
0x180073827  jz      short loc_180073853
0x180073829  mov     rax, [rsp+78h+var_30]
0x18007382e  test    rax, rax
0x180073831  jz      short loc_180073847
0x180073833  mov     rcx, rax
0x180073836  call    cs:__imp_BcdCloseObject
0x18007383d  nop     dword ptr [rax+rax+00h]
0x180073842  mov     rcx, [rsp+78h+var_38]
0x180073847  call    cs:__imp_BcdCloseStore
0x18007384e  nop     dword ptr [rax+rax+00h]
0x180073853  mov     eax, ebx
0x180073855  mov     rcx, [rsp+78h+var_18]
0x18007385a  xor     rcx, rsp; StackCookie
0x18007385d  call    __security_check_cookie
0x180073862  mov     rbx, [rsp+78h+arg_8]
0x18007386a  add     rsp, 70h
0x18007386e  pop     rdi
0x18007386f  retn
0x180122af2  push    rbp
0x180122af4  sub     rsp, 20h
0x180122af8  mov     rbp, rdx
0x180122afb  mov     rcx, [rbp+28h]; lpMem
0x180122aff  test    rcx, rcx
0x180122b02  jz      short loc_180122B0A
0x180122b04  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180122b09  nop
0x180122b0a  mov     rcx, [rbp+38h]; lpMem
0x180122b0e  test    rcx, rcx
0x180122b11  jz      short loc_180122B19
0x180122b13  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180122b18  nop
0x180122b19  mov     rcx, [rbp+40h]
0x180122b1d  test    rcx, rcx
0x180122b20  jz      short loc_180122B4B
0x180122b22  mov     rax, [rbp+48h]
0x180122b26  test    rax, rax
0x180122b29  jz      short loc_180122B3E
0x180122b2b  mov     rcx, rax
0x180122b2e  call    cs:__imp_BcdCloseObject
0x180122b35  nop     dword ptr [rax+rax+00h]
0x180122b3a  mov     rcx, [rbp+40h]
0x180122b3e  call    cs:__imp_BcdCloseStore
0x180122b45  nop     dword ptr [rax+rax+00h]
0x180122b4a  nop
0x180122b4b  add     rsp, 20h
0x180122b4f  pop     rbp
0x180122b50  retn
```
