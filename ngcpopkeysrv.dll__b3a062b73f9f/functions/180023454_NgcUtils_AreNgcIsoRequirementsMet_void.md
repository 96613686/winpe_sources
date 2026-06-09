# NgcUtils::AreNgcIsoRequirementsMet(void)

- ea: `0x180023454`
- end: `0x1800234a6`
- name: `?AreNgcIsoRequirementsMet@NgcUtils@@YA_NXZ`
- size: `82`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180023838`

## callees

- `0x18002234c`
- `0x180023454`
- `0x1800234ac`
- `0x1800236e8`
- `0x180023894`

## string_xrefs

- `0x18002348a`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180023478`: `NgcIso is incompatible with CDF.`

## pseudocode

```c
char __fastcall NgcUtils::AreNgcIsoRequirementsMet(NgcUtils *this)
{
  unsigned int v1; // edx
  NgcUtils *v2; // rcx
  NgcUtils *v3; // rcx
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !NgcUtils::DoesTPMSupportNgcIso(this) || !NgcUtils::IsNgcIsoPackagePresent(v2, v1) )
    return 0;
  if ( NgcUtils::IsCdfAllowed(v3) )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"NgcIso is incompatible with CDF.",
      v5);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180023454  sub     rsp, 38h
0x180023458  call    ?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ; NgcUtils::DoesTPMSupportNgcIso(void)
0x18002345d  test    al, al
0x18002345f  jz      short loc_18002349B
0x180023461  call    ?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ; NgcUtils::IsNgcIsoPackagePresent(void)
0x180023466  test    al, al
0x180023468  jz      short loc_18002349B
0x18002346a  call    ?IsCdfAllowed@NgcUtils@@YA_NXZ; NgcUtils::IsCdfAllowed(void)
0x18002346f  test    al, al
0x180023471  jz      short loc_1800234A2
0x180023473  mov     rcx, [rsp+38h]; this
0x180023478  lea     rax, aNgcisoIsIncomp; "NgcIso is incompatible with CDF."
0x18002347f  mov     r9d, 80090029h; char *
0x180023485  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002348a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023491  mov     edx, 84h; void *
0x180023496  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002349b  xor     al, al
0x18002349d  add     rsp, 38h
0x1800234a1  retn
0x1800234a2  mov     al, 1
0x1800234a4  jmp     short loc_18002349D
```
