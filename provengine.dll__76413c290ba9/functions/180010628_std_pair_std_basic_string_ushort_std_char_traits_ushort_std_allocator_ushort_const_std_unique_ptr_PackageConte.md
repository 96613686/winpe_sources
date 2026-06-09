# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>(void)

- ea: `0x180010628`
- end: `0x18001069b`
- name: `??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800101cc`
- `0x180021294`
- `0x180035378`
- `0x180035c84`
- `0x180036758`

## callees

- `0x180010628`
- `0x1800111d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010657`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010660`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010670`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010657`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010660`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010670`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall std::pair<std::wstring const,std::unique_ptr<PackageContext>>::~pair<std::wstring const,std::unique_ptr<PackageContext>>(
        __int64 a1)
{
  PackageEnroller **v1; // rdi
  PackageEnroller *v3; // rsi
  __int64 result; // rax

  v1 = *(PackageEnroller ***)(a1 + 32);
  if ( v1 )
  {
    v3 = v1[1];
    if ( v3 )
    {
      PackageEnroller::~PackageEnroller(v1[1]);
      operator delete(v3);
    }
    operator delete(v1);
  }
  if ( *(_QWORD *)(a1 + 24) >= 8u )
    operator delete(*(void **)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180010628  mov     [rsp+arg_0], rbx
0x18001062d  mov     [rsp+arg_8], rsi
0x180010632  push    rdi
0x180010633  sub     rsp, 20h
0x180010637  mov     rdi, [rcx+20h]
0x18001063b  mov     rbx, rcx
0x18001063e  test    rdi, rdi
0x180010641  jz      short loc_180010666
0x180010643  mov     rsi, [rdi+8]
0x180010647  test    rsi, rsi
0x18001064a  jz      short loc_18001065D
0x18001064c  mov     rcx, rsi; this
0x18001064f  call    ??1PackageEnroller@@QEAA@XZ; PackageEnroller::~PackageEnroller(void)
0x180010654  mov     rcx, rsi
0x180010657  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001065d  mov     rcx, rdi
0x180010660  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010666  cmp     qword ptr [rbx+18h], 8
0x18001066b  jb      short loc_180010676
0x18001066d  mov     rcx, [rbx]
0x180010670  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010676  mov     rsi, [rsp+28h+arg_8]
0x18001067b  xor     eax, eax
0x18001067d  mov     qword ptr [rbx+18h], 7
0x180010685  mov     qword ptr [rbx+10h], 0
0x18001068d  mov     [rbx], ax
0x180010690  mov     rbx, [rsp+28h+arg_0]
0x180010695  add     rsp, 20h
0x180010699  pop     rdi
0x18001069a  retn
```
