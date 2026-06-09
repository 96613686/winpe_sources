# CAUtilGetCADisplayName(ulong,ushort *,ushort * *)

- ea: `0x1800066f8`
- end: `0x1800067b2`
- name: `?CAUtilGetCADisplayName@@YAHKPEAGPEAPEAG@Z`
- size: `186`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002c0f0`

## callees

- `0x1800059ec`
- `0x1800066f8`

## import_xrefs

- `certca!__imp_CAFindByName` at `0x180006733`
- `certca!__imp_CAFindByName` at `0x180006733`
- `certca!__imp_CACloseCA` at `0x180006794`
- `certca!__imp_CACloseCA` at `0x180006794`
- `certca!__imp_CAGetCAProperty` at `0x180006751`
- `certca!__imp_CAGetCAProperty` at `0x180006751`
- `certca!__imp_CAFreeCAProperty` at `0x180006785`
- `certca!__imp_CAFreeCAProperty` at `0x180006785`

## pseudocode

```c
_BOOL8 __fastcall CAUtilGetCADisplayName(unsigned int a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  BOOL v3; // ebx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  unsigned __int16 **v8; // rdx
  unsigned __int16 *v9; // rax
  __int64 v11; // [rsp+38h] [rbp+18h] BYREF
  unsigned __int16 **v12; // [rsp+48h] [rbp+28h] BYREF

  v3 = 0;
  v11 = 0;
  v12 = 0;
  if ( !a2 || !a3 )
    return v3;
  *a3 = 0;
  v5 = CAFindByName(a2, 0, a1, &v11);
  v6 = v11;
  if ( v11 && v5 >= 0 )
  {
    v7 = CAGetCAProperty(v11, L"displayName", &v12);
    v8 = v12;
    if ( !v12 )
      goto LABEL_11;
    if ( v7 < 0 )
    {
      v6 = v11;
      goto LABEL_9;
    }
    v9 = LocalAllocAndCopyWStr(*v12);
    *a3 = v9;
    v3 = v9 != 0;
    v6 = v11;
  }
  v8 = v12;
LABEL_9:
  if ( !v8 )
    goto LABEL_12;
  CAFreeCAProperty(v6, v8);
LABEL_11:
  v6 = v11;
LABEL_12:
  if ( v6 )
    CACloseCA(v6);
  return v3;
}

```

## disassembly

```asm
0x1800066f8  mov     [rsp-8+arg_0], rbx
0x1800066fd  mov     [rsp-8+arg_10], rdi
0x180006702  push    rbp
0x180006703  mov     rbp, rsp
0x180006706  sub     rsp, 20h
0x18000670a  xor     ebx, ebx
0x18000670c  mov     rdi, r8
0x18000670f  mov     [rbp+arg_8], rbx
0x180006713  mov     rax, rdx
0x180006716  mov     [rbp+arg_18], rbx
0x18000671a  test    rdx, rdx
0x18000671d  jz      short loc_18000679A
0x18000671f  test    r8, r8
0x180006722  jz      short loc_18000679A
0x180006724  mov     [r8], rbx
0x180006727  lea     r9, [rbp+arg_8]
0x18000672b  mov     r8d, ecx
0x18000672e  xor     edx, edx
0x180006730  mov     rcx, rax
0x180006733  call    cs:__imp_CAFindByName
0x180006739  mov     rcx, [rbp+arg_8]
0x18000673d  test    rcx, rcx
0x180006740  jz      short loc_18000677C
0x180006742  test    eax, eax
0x180006744  js      short loc_18000677C
0x180006746  lea     r8, [rbp+arg_18]
0x18000674a  lea     rdx, aDisplayname; "displayName"
0x180006751  call    cs:__imp_CAGetCAProperty
0x180006757  mov     rdx, [rbp+arg_18]
0x18000675b  test    rdx, rdx
0x18000675e  jz      short loc_18000678B
0x180006760  test    eax, eax
0x180006762  js      short loc_1800067AC
0x180006764  mov     rcx, [rdx]; Src
0x180006767  call    ?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z; LocalAllocAndCopyWStr(ushort *)
0x18000676c  lea     ecx, [rbx+1]
0x18000676f  mov     [rdi], rax
0x180006772  test    rax, rax
0x180006775  cmovnz  ebx, ecx
0x180006778  mov     rcx, [rbp+arg_8]
0x18000677c  mov     rdx, [rbp+arg_18]
0x180006780  test    rdx, rdx
0x180006783  jz      short loc_18000678F
0x180006785  call    cs:__imp_CAFreeCAProperty
0x18000678b  mov     rcx, [rbp+arg_8]
0x18000678f  test    rcx, rcx
0x180006792  jz      short loc_18000679A
0x180006794  call    cs:__imp_CACloseCA
0x18000679a  mov     rdi, [rsp+20h+arg_10]
0x18000679f  mov     eax, ebx
0x1800067a1  mov     rbx, [rsp+20h+arg_0]
0x1800067a6  add     rsp, 20h
0x1800067aa  pop     rbp
0x1800067ab  retn
0x1800067ac  mov     rcx, [rbp+arg_8]
0x1800067b0  jmp     short loc_180006780
```
