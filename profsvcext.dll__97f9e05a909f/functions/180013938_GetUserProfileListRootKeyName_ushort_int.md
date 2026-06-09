# GetUserProfileListRootKeyName(ushort * *,int *)

- ea: `0x180013938`
- end: `0x1800139e4`
- name: `?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z`
- size: `172`
- prototype: `__int64 __fastcall(unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001375c`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x180011084`
- `0x180012e0c`
- `0x180013938`
- `0x180013af4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013997`

## string_xrefs

- `0x1800139ba`: `onecore\internal\ds\inc\profiles\sid.h`

## pseudocode

```c
__int64 __fastcall GetUserProfileListRootKeyName(unsigned __int16 **a1, int *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HANDLE ProcessHeap; // rax
  __int64 v7; // rdx
  __int64 v9[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  memset(v9, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
              v9,
              a2,
              L"System\\CurrentControlSet\\Control\\ProfileList",
              L"RedirectionKey") < 0 )
  {
    ProcessHeap = GetProcessHeap();
    v3 = _AllocString<CTHeapAllocPolicy>(
           (__int64)ProcessHeap,
           v7,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           a1);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = 90;
      goto LABEL_6;
    }
LABEL_7:
    v4 = 0;
    goto LABEL_8;
  }
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(v9, a1);
  v4 = v3;
  if ( v3 >= 0 )
    goto LABEL_7;
  v5 = 82;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
    (const char *)(unsigned int)v3,
    v9[0]);
LABEL_8:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v9);
  return v4;
}

```

## disassembly

```asm
0x180013938  mov     rax, rsp
0x18001393b  push    rbx
0x18001393c  sub     rsp, 40h
0x180013940  mov     rbx, rcx
0x180013943  mov     qword ptr [rcx], 0
0x18001394a  mov     qword ptr [rax-28h], 0
0x180013952  mov     qword ptr [rax-20h], 0
0x18001395a  mov     qword ptr [rax-18h], 0
0x180013962  lea     r9, aRedirectionkey; "RedirectionKey"
0x180013969  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pro"...
0x180013970  lea     rcx, [rax-28h]
0x180013974  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180013979  test    eax, eax
0x18001397b  js      short loc_180013997
0x18001397d  mov     rdx, rbx
0x180013980  lea     rcx, [rsp+48h+var_28]
0x180013985  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x18001398a  mov     ebx, eax
0x18001398c  test    eax, eax
0x18001398e  jns     short loc_1800139D0
0x180013990  mov     edx, 52h ; 'R'
0x180013995  jmp     short loc_1800139BA
0x180013997  call    cs:__imp_GetProcessHeap
0x18001399d  mov     r9, rbx
0x1800139a0  lea     r8, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800139a7  mov     rcx, rax
0x1800139aa  call    ??$_AllocString@VCTHeapAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTHeapAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800139af  mov     ebx, eax
0x1800139b1  test    eax, eax
0x1800139b3  jns     short loc_1800139D0
0x1800139b5  mov     edx, 5Ah ; 'Z'; void *
0x1800139ba  lea     r8, aOnecoreInterna_4; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x1800139c1  mov     r9d, eax; char *
0x1800139c4  mov     rcx, [rsp+48h]; this
0x1800139c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800139ce  jmp     short loc_1800139D2
0x1800139d0  xor     ebx, ebx
0x1800139d2  lea     rcx, [rsp+48h+var_28]
0x1800139d7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800139dc  mov     eax, ebx
0x1800139de  add     rsp, 40h
0x1800139e2  pop     rbx
0x1800139e3  retn
```
