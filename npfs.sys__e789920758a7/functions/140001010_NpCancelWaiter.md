# NpCancelWaiter

- ea: `0x140001010`
- end: `0x1400012f9`
- name: `NpCancelWaiter`
- size: `745`
- prototype: `__int64 __fastcall(_QWORD *, const UNICODE_STRING *, int, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fb40`
- `0x1400107c0`
- `0x140010ef4`

## callees

- `0x140001010`
- `0x140001e10`
- `0x140002760`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000109a`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14000109a`
- `ntoskrnl!ExAllocatePool2` at `0x14000114e`
- `ntoskrnl!ExAllocatePool2` at `0x14000114e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400010eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400010eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001297`
- `ntoskrnl!ObfDereferenceObject` at `0x140001286`
- `ntoskrnl!ObfDereferenceObject` at `0x140001286`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400010aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400010aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010ce`
- `ntoskrnl!KeCancelTimer` at `0x1400011fc`
- `ntoskrnl!KeCancelTimer` at `0x1400011fc`

## pseudocode

```c
__int64 __fastcall NpCancelWaiter(_QWORD *a1, const UNICODE_STRING *a2, int a3, __int64 a4)
{
  __int64 Length; // rax
  __int64 v9; // rsi
  KIRQL v10; // al
  _QWORD *v11; // rbx
  KIRQL v12; // r12
  USHORT v14; // r13
  __int64 v15; // rax
  __int16 v16; // cx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // r13
  BOOLEAN v21; // al
  _QWORD *v22; // rcx
  bool v23; // zf
  __int64 v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  PVOID *v27; // rbx
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-148h] BYREF
  __int64 v29; // [rsp+30h] [rbp-138h]
  _QWORD *v30; // [rsp+38h] [rbp-130h]
  _QWORD *v31; // [rsp+48h] [rbp-120h]
  _BYTE v32[208]; // [rsp+50h] [rbp-118h] BYREF

  Length = a2->Length;
  DestinationString = 0;
  if ( (unsigned __int16)Length > 0xC8u )
  {
    DestinationString.Buffer = (PWSTR)ExAllocatePool2(64, Length, 1950773326);
    if ( !DestinationString.Buffer )
      return 3221225626LL;
  }
  else
  {
    DestinationString.Buffer = (PWSTR)v32;
  }
  DestinationString.Length = 0;
  v9 = 0;
  DestinationString.MaximumLength = a2->Length;
  RtlUpcaseUnicodeString(&DestinationString, a2, 0);
  v10 = KeAcquireSpinLockRaiseToDpc(a1 + 2);
  v11 = (_QWORD *)*a1;
  v12 = v10;
  if ( (_QWORD *)*a1 != a1 )
  {
    v14 = DestinationString.Length;
    do
    {
      v30 = v11 - 5;
      v15 = *(v11 - 5);
      v29 = v15;
      v16 = *(_WORD *)(v15 + 152);
      if ( v16 )
      {
        if ( v14 == v16 && !memcmp((const void *)(v15 + 160), DestinationString.Buffer, v14) )
        {
LABEL_14:
          v18 = *v11;
          if ( *(_QWORD **)(*v11 + 8LL) != v11 || (v31 = v11 + 1, v19 = (_QWORD *)v11[1], (_QWORD *)*v19 != v11) )
LABEL_28:
            __fastfail(3u);
          *v19 = v18;
          v20 = v11;
          *(_QWORD *)(v18 + 8) = v19;
          v11 = v19;
          v21 = KeCancelTimer((PKTIMER)(v29 + 72));
          v22 = v30;
          v23 = v21 == 0;
          v24 = v29;
          if ( v23 )
          {
            *(_QWORD *)v29 = 0;
            *v22 = 0;
          }
          else
          {
            *(_QWORD *)(v29 + 136) = v9;
            v9 = v24;
          }
          if ( _InterlockedExchange64(v20 - 8, 0) )
          {
            *(v20 - 14) = 0;
            *((_DWORD *)v20 - 30) = a3;
            v25 = *(_QWORD **)(a4 + 8);
            if ( *v25 != a4 )
              goto LABEL_28;
            v26 = v31;
            *v20 = a4;
            *v26 = v25;
            *v25 = v20;
            *(_QWORD *)(a4 + 8) = v20;
          }
          else
          {
            *v22 = 0;
          }
          v14 = DestinationString.Length;
        }
      }
      else
      {
        v17 = *(v11 - 18);
        if ( *(_DWORD *)(v17 + 8) == v14 && !memcmp((const void *)(v17 + 14), DestinationString.Buffer, v14) )
          goto LABEL_14;
      }
      v11 = (_QWORD *)*v11;
    }
    while ( v11 != a1 );
  }
  KeReleaseSpinLock(a1 + 2, v12);
  if ( (_BYTE *)DestinationString.Buffer != v32 )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  while ( v9 )
  {
    v27 = (PVOID *)v9;
    v9 = *(_QWORD *)(v9 + 136);
    ObfDereferenceObject(v27[18]);
    ExFreePoolWithTag(v27, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140001010  push    rbx
0x140001012  push    rbp
0x140001013  push    rdi
0x140001014  push    r14
0x140001016  sub     rsp, 148h
0x14000101d  mov     rax, cs:__security_cookie
0x140001024  xor     rax, rsp
0x140001027  mov     [rsp+168h+var_48], rax
0x14000102f  movzx   eax, word ptr [rdx]
0x140001032  mov     rdi, rcx
0x140001035  mov     ecx, 0C8h
0x14000103a  xorps   xmm0, xmm0
0x14000103d  mov     rbp, r9
0x140001040  mov     r14d, r8d
0x140001043  mov     rbx, rdx
0x140001046  movups  xmmword ptr [rsp+168h+DestinationString.Length], xmm0
0x14000104b  cmp     ax, cx
0x14000104e  ja      loc_140001140
0x140001054  lea     rax, [rsp+168h+var_118]
0x140001059  mov     [rsp+168h+DestinationString.Buffer], rax
0x14000105e  mov     [rsp+168h+arg_10], rsi
0x140001066  lea     rcx, [rsp+168h+DestinationString]; DestinationString
0x14000106b  xor     eax, eax
0x14000106d  mov     [rsp+168h+var_28], r12
0x140001075  mov     [rsp+168h+DestinationString.Length], ax
0x14000107a  xor     r8d, r8d; AllocateDestinationString
0x14000107d  movzx   eax, word ptr [rbx]
0x140001080  mov     rdx, rbx; SourceString
0x140001083  mov     [rsp+168h+var_30], r13
0x14000108b  xor     esi, esi
0x14000108d  mov     [rsp+168h+DestinationString.MaximumLength], ax
0x140001092  mov     [rsp+168h+var_38], r15
0x14000109a  call    cs:__imp_RtlUpcaseUnicodeString
0x1400010a1  nop     dword ptr [rax+rax+00h]
0x1400010a6  lea     rcx, [rdi+10h]; SpinLock
0x1400010aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400010b1  nop     dword ptr [rax+rax+00h]
0x1400010b6  mov     rbx, [rdi]
0x1400010b9  movzx   r12d, al
0x1400010bd  cmp     rbx, rdi
0x1400010c0  jnz     loc_14000116F
0x1400010c6  movzx   edx, r12b; NewIrql
0x1400010ca  lea     rcx, [rdi+10h]; SpinLock
0x1400010ce  call    cs:__imp_KeReleaseSpinLock
0x1400010d5  nop     dword ptr [rax+rax+00h]
0x1400010da  mov     rcx, [rsp+168h+DestinationString.Buffer]; P
0x1400010df  lea     rax, [rsp+168h+var_118]
0x1400010e4  cmp     rcx, rax
0x1400010e7  jz      short loc_1400010F7
0x1400010e9  xor     edx, edx; Tag
0x1400010eb  call    cs:__imp_ExFreePoolWithTag
0x1400010f2  nop     dword ptr [rax+rax+00h]
0x1400010f7  test    rsi, rsi
0x1400010fa  jnz     loc_140001275
0x140001100  mov     r13, [rsp+168h+var_30]
0x140001108  xor     eax, eax
0x14000110a  mov     r12, [rsp+168h+var_28]
0x140001112  mov     rsi, [rsp+168h+arg_10]
0x14000111a  mov     r15, [rsp+168h+var_38]
0x140001122  mov     rcx, [rsp+168h+var_48]
0x14000112a  xor     rcx, rsp; StackCookie
0x14000112d  call    __security_check_cookie
0x140001132  add     rsp, 148h
0x140001139  pop     r14
0x14000113b  pop     rdi
0x14000113c  pop     rbp
0x14000113d  pop     rbx
0x14000113e  retn
0x140001140  mov     rdx, rax
0x140001143  mov     ecx, 40h ; '@'
0x140001148  mov     r8d, 7446704Eh
0x14000114e  call    cs:__imp_ExAllocatePool2
0x140001155  nop     dword ptr [rax+rax+00h]
0x14000115a  mov     [rsp+168h+DestinationString.Buffer], rax
0x14000115f  test    rax, rax
0x140001162  jnz     loc_14000105E
0x140001168  mov     eax, 0C000009Ah
0x14000116d  jmp     short loc_140001122
0x14000116f  movzx   r13d, [rsp+168h+DestinationString.Length]
0x140001175  lea     rax, [rbx-28h]
0x140001179  mov     [rsp+168h+var_130], rax
0x14000117e  mov     rax, [rax]
0x140001181  mov     [rsp+168h+var_138], rax
0x140001186  movzx   ecx, word ptr [rax+98h]
0x14000118d  test    cx, cx
0x140001190  jnz     loc_1400012D1
0x140001196  mov     rcx, [rbx-90h]
0x14000119d  movzx   eax, r13w
0x1400011a1  cmp     [rcx+8], eax
0x1400011a4  jnz     loc_140001264
0x1400011aa  mov     rdx, [rsp+168h+DestinationString.Buffer]; Buf2
0x1400011af  add     rcx, 0Eh; Buf1
0x1400011b3  movzx   r8d, r13w; Size
0x1400011b7  call    memcmp
0x1400011bc  test    eax, eax
0x1400011be  jnz     loc_140001264
0x1400011c4  mov     rcx, [rbx]
0x1400011c7  cmp     [rcx+8], rbx
0x1400011cb  jnz     loc_1400012CA
0x1400011d1  lea     rax, [rbx+8]
0x1400011d5  mov     [rsp+168h+var_120], rax
0x1400011da  mov     rax, [rax]
0x1400011dd  cmp     [rax], rbx
0x1400011e0  jnz     loc_1400012CA
0x1400011e6  mov     [rax], rcx
0x1400011e9  mov     r13, rbx
0x1400011ec  mov     [rcx+8], rax
0x1400011f0  mov     rbx, rax
0x1400011f3  mov     rcx, [rsp+168h+var_138]
0x1400011f8  add     rcx, 48h ; 'H'; PKTIMER
0x1400011fc  call    cs:__imp_KeCancelTimer
0x140001203  nop     dword ptr [rax+rax+00h]
0x140001208  mov     rcx, [rsp+168h+var_130]
0x14000120d  test    al, al
0x14000120f  mov     rax, [rsp+168h+var_138]
0x140001214  jz      loc_1400012B7
0x14000121a  mov     [rax+88h], rsi
0x140001221  mov     rsi, rax
0x140001224  xor     eax, eax
0x140001226  xchg    rax, [r13-40h]
0x14000122a  test    rax, rax
0x14000122d  jz      short loc_1400012AE
0x14000122f  mov     qword ptr [r13-70h], 0
0x140001237  mov     [r13-78h], r14d
0x14000123b  mov     rax, [rbp+8]
0x14000123f  cmp     [rax], rbp
0x140001242  jnz     loc_1400012CA
0x140001248  mov     rdx, [rsp+168h+var_120]
0x14000124d  mov     rcx, r13
0x140001250  mov     [r13+0], rbp
0x140001254  mov     [rdx], rax
0x140001257  mov     [rax], rcx
0x14000125a  mov     [rbp+8], rcx
0x14000125e  movzx   r13d, [rsp+168h+DestinationString.Length]
0x140001264  mov     rbx, [rbx]
0x140001267  cmp     rbx, rdi
0x14000126a  jz      loc_1400010C6
0x140001270  jmp     loc_140001175
0x140001275  mov     rbx, rsi
0x140001278  mov     rsi, [rsi+88h]
0x14000127f  mov     rcx, [rbx+90h]; Object
0x140001286  call    cs:__imp_ObfDereferenceObject
0x14000128d  nop     dword ptr [rax+rax+00h]
0x140001292  xor     edx, edx; Tag
0x140001294  mov     rcx, rbx; P
0x140001297  call    cs:__imp_ExFreePoolWithTag
0x14000129e  nop     dword ptr [rax+rax+00h]
0x1400012a3  test    rsi, rsi
0x1400012a6  jz      loc_140001100
0x1400012ac  jmp     short loc_140001275
0x1400012ae  mov     qword ptr [rcx], 0
0x1400012b5  jmp     short loc_14000125E
0x1400012b7  mov     qword ptr [rax], 0
0x1400012be  mov     qword ptr [rcx], 0
0x1400012c5  jmp     loc_140001224
0x1400012ca  mov     ecx, 3
0x1400012cf  int     29h; Win8: RtlFailFast(ecx)
0x1400012d1  cmp     r13w, cx
0x1400012d5  jnz     short loc_140001264
0x1400012d7  mov     rdx, [rsp+168h+DestinationString.Buffer]; Buf2
0x1400012dc  lea     rcx, [rax+0A0h]; Buf1
0x1400012e3  movzx   r8d, r13w; Size
0x1400012e7  call    memcmp
0x1400012ec  test    eax, eax
0x1400012ee  jnz     loc_140001264
0x1400012f4  jmp     loc_1400011C4
```
