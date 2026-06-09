# KsReleaseControl_wrapper

- ea: `0x180071780`
- end: `0x180071988`
- name: `KsReleaseControl_wrapper`
- size: `520`
- prototype: `void __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180019cb0`
- `0x180058ce0`
- `0x18005a750`
- `0x180071780`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800717b7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800717b7`

## string_xrefs

- `0x180071917`: `The driver attempts to release a filter mutex acquired in a different thread.`
- `0x1800718f3`: `The driver attempts to release a filter mutex though it was not acquired yet.`

## pseudocode

```c
void __fastcall KsReleaseControl_wrapper(PVOID Object)
{
  __int64 v2; // rdi
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rbp
  __int64 v4; // r9
  PVOID v5; // r8
  PVOID v6; // r8
  __int64 v7; // rax
  const char *v8; // rcx
  int v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  v2 = 0;
  Descriptor = KsGetDevice(Object)[1].Descriptor;
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsReleaseControl should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v2 = (*(__int64 (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 8))(Descriptor);
    (*(void (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 72))(Descriptor);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v2 )
  {
    if ( *((_DWORD *)Object - 20) == 3 )
      v5 = (PVOID)((*((_QWORD *)Object - 11) + 128LL) & -(__int64)(*((_QWORD *)Object - 11) != 0));
    else
      v5 = Object;
    LOBYTE(v4) = 1;
    (*(void (__fastcall **)(__int64, __int64, PVOID, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v2 + 152,
      136,
      v5,
      v4,
      &v10);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v2 )
  {
    v6 = *((_DWORD *)Object - 20) == 3
       ? (PVOID)((*((_QWORD *)Object - 11) + 128LL) & -(__int64)(*((_QWORD *)Object - 11) != 0))
       : Object;
    LOBYTE(v4) = 1;
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PVOID, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v2 + 152),
      136,
      v6,
      v4,
      v9,
      &v10);
    if ( v10 )
    {
      if ( !*(_BYTE *)(v10 + 128) )
      {
        v7 = KsVerifierUtilTable;
        v8 = "The driver attempts to release a filter mutex though it was not acquired yet.";
LABEL_22:
        (*(void (__fastcall **)(const char *, __int64, __int64))(v7 + 88))(v8, 528394, v2);
        goto LABEL_24;
      }
      v7 = KsVerifierUtilTable;
      if ( *(struct _KTHREAD **)(v10 + 112) != KeGetCurrentThread() )
      {
        v8 = "The driver attempts to release a filter mutex acquired in a different thread.";
        goto LABEL_22;
      }
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(KsVerifierUtilTable + 64))(&v10, 136, v2 + 152);
    }
  }
LABEL_24:
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(const _KSDEVICE_DESCRIPTOR *))(KsVerifierUtilTable + 80))(Descriptor);
  KsReleaseControl(Object);
}

```

## disassembly

```asm
0x180071780  mov     [rsp+arg_0], rbx
0x180071785  mov     [rsp+arg_10], rbp
0x18007178a  push    rsi
0x18007178b  push    rdi
0x18007178c  push    r14
0x18007178e  sub     rsp, 40h
0x180071792  mov     rbx, rcx
0x180071795  mov     [rsp+58h+arg_8], 0
0x18007179e  xor     edi, edi
0x1800717a0  call    KsGetDevice
0x1800717a5  mov     sil, 8
0x1800717a8  mov     rbp, [rax+40h]
0x1800717ac  mov     eax, cs:KsXdvExtLevel
0x1800717b2  test    sil, al
0x1800717b5  jz      short loc_1800717E3
0x1800717b7  call    cs:__imp_KeGetCurrentIrql
0x1800717be  nop     dword ptr [rax+rax+00h]
0x1800717c3  test    al, al
0x1800717c5  jz      short loc_1800717E3
0x1800717c7  mov     rax, cs:KsVerifierUtilTable
0x1800717ce  lea     rcx, aKsreleasecontr; "KsReleaseControl should only be called "...
0x1800717d5  mov     edx, 81009h
0x1800717da  mov     rax, [rax+60h]
0x1800717de  call    _guard_dispatch_icall
0x1800717e3  mov     eax, cs:KsXdvExtLevel
0x1800717e9  test    al, 18h
0x1800717eb  jz      short loc_180071816
0x1800717ed  mov     rax, cs:KsVerifierUtilTable
0x1800717f4  mov     rcx, rbp
0x1800717f7  mov     rax, [rax+8]
0x1800717fb  call    _guard_dispatch_icall
0x180071800  mov     rcx, cs:KsVerifierUtilTable
0x180071807  mov     rdi, rax
0x18007180a  mov     rax, [rcx+48h]
0x18007180e  mov     rcx, rbp
0x180071811  call    _guard_dispatch_icall
0x180071816  mov     ecx, cs:KsXdvExtLevel
0x18007181c  mov     r14d, 88h
0x180071822  test    sil, cl
0x180071825  jz      short loc_180071872
0x180071827  test    rdi, rdi
0x18007182a  jz      short loc_180071872
0x18007182c  cmp     dword ptr [rbx-50h], 3
0x180071830  jnz     short loc_180071848
0x180071832  mov     rax, [rbx-58h]
0x180071836  lea     rcx, [rax+80h]
0x18007183d  neg     rax
0x180071840  sbb     r8, r8
0x180071843  and     r8, rcx
0x180071846  jmp     short loc_18007184B
0x180071848  mov     r8, rbx
0x18007184b  mov     rax, cs:KsVerifierUtilTable
0x180071852  lea     rdx, [rsp+58h+arg_8]
0x180071857  mov     [rsp+58h+var_38], rdx
0x18007185c  lea     rcx, [rdi+98h]
0x180071863  mov     r9b, 1
0x180071866  mov     edx, r14d
0x180071869  mov     rax, [rax+28h]
0x18007186d  call    _guard_dispatch_icall
0x180071872  mov     eax, cs:KsXdvExtLevel
0x180071878  test    sil, al
0x18007187b  jz      loc_18007194F
0x180071881  test    rdi, rdi
0x180071884  jz      loc_18007194F
0x18007188a  cmp     dword ptr [rbx-50h], 3
0x18007188e  jnz     short loc_1800718A6
0x180071890  mov     rax, [rbx-58h]
0x180071894  lea     rcx, [rax+80h]
0x18007189b  neg     rax
0x18007189e  sbb     r8, r8
0x1800718a1  and     r8, rcx
0x1800718a4  jmp     short loc_1800718A9
0x1800718a6  mov     r8, rbx
0x1800718a9  mov     rax, cs:KsVerifierUtilTable
0x1800718b0  lea     rcx, [rsp+58h+arg_8]
0x1800718b5  mov     [rsp+58h+var_30], rcx
0x1800718ba  lea     rsi, [rdi+98h]
0x1800718c1  mov     rcx, [rsi]
0x1800718c4  mov     r9b, 1
0x1800718c7  mov     edx, r14d
0x1800718ca  mov     byte ptr [rsp+58h+var_38], 1
0x1800718cf  mov     rax, [rax+20h]
0x1800718d3  call    _guard_dispatch_icall
0x1800718d8  mov     r9, [rsp+58h+arg_8]
0x1800718dd  test    r9, r9
0x1800718e0  jz      short loc_18007194F
0x1800718e2  cmp     byte ptr [r9+80h], 0
0x1800718ea  jnz     short loc_1800718FC
0x1800718ec  mov     rax, cs:KsVerifierUtilTable
0x1800718f3  lea     rcx, aTheDriverAttem; "The driver attempts to release a filter"...
0x1800718fa  jmp     short loc_18007191E
0x1800718fc  mov     rax, gs:188h
0x180071905  mov     r9, [rsp+58h+arg_8]
0x18007190a  cmp     [r9+70h], rax
0x18007190e  mov     rax, cs:KsVerifierUtilTable
0x180071915  jz      short loc_18007193B
0x180071917  lea     rcx, aTheDriverAttem_4; "The driver attempts to release a filter"...
0x18007191e  mov     rax, [rax+58h]
0x180071922  mov     edx, 8100Ah
0x180071927  mov     dword ptr [rsp+58h+var_30], r14d
0x18007192c  mov     r8, rdi
0x18007192f  mov     [rsp+58h+var_38], rsi
0x180071934  call    _guard_dispatch_icall
0x180071939  jmp     short loc_18007194F
0x18007193b  mov     rax, [rax+40h]
0x18007193f  lea     rcx, [rsp+58h+arg_8]
0x180071944  mov     r8, rsi
0x180071947  mov     edx, r14d
0x18007194a  call    _guard_dispatch_icall
0x18007194f  mov     eax, cs:KsXdvExtLevel
0x180071955  test    al, 18h
0x180071957  jz      short loc_18007196C
0x180071959  mov     rax, cs:KsVerifierUtilTable
0x180071960  mov     rcx, rbp
0x180071963  mov     rax, [rax+50h]
0x180071967  call    _guard_dispatch_icall
0x18007196c  mov     rcx, rbx; Object
0x18007196f  call    KsReleaseControl
0x180071974  mov     rbx, [rsp+58h+arg_0]
0x180071979  mov     rbp, [rsp+58h+arg_10]
0x18007197e  add     rsp, 40h
0x180071982  pop     r14
0x180071984  pop     rdi
0x180071985  pop     rsi
0x180071986  retn
```
