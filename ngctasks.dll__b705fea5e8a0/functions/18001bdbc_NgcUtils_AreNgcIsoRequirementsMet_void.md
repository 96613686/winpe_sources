# NgcUtils::AreNgcIsoRequirementsMet(void)

- ea: `0x18001bdbc`
- end: `0x18001be0e`
- name: `?AreNgcIsoRequirementsMet@NgcUtils@@YA_NXZ`
- size: `82`
- prototype: `char __fastcall(NgcUtils *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c1f8`

## callees

- `0x18001bdbc`
- `0x18001be14`
- `0x18001c0a8`
- `0x18001c254`
- `0x18001c520`

## string_xrefs

- `0x18001bdf2`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001bde0`: `NgcIso is incompatible with CDF.`

## pseudocode

```c
char __fastcall NgcUtils::AreNgcIsoRequirementsMet(NgcUtils *this)
{
  NgcUtils *v1; // rcx
  NgcUtils *v2; // rcx
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !NgcUtils::DoesTPMSupportNgcIso(this) || !NgcUtils::IsNgcIsoPackagePresent(v1) )
    return 0;
  if ( NgcUtils::IsCdfAllowed(v2) )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"NgcIso is incompatible with CDF.",
      v4);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001bdbc  sub     rsp, 38h
0x18001bdc0  call    ?DoesTPMSupportNgcIso@NgcUtils@@YA_NXZ; NgcUtils::DoesTPMSupportNgcIso(void)
0x18001bdc5  test    al, al
0x18001bdc7  jz      short loc_18001BE03
0x18001bdc9  call    ?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ; NgcUtils::IsNgcIsoPackagePresent(void)
0x18001bdce  test    al, al
0x18001bdd0  jz      short loc_18001BE03
0x18001bdd2  call    ?IsCdfAllowed@NgcUtils@@YA_NXZ; NgcUtils::IsCdfAllowed(void)
0x18001bdd7  test    al, al
0x18001bdd9  jz      short loc_18001BE0A
0x18001bddb  mov     rcx, [rsp+38h]; this
0x18001bde0  lea     rax, aNgcisoIsIncomp; "NgcIso is incompatible with CDF."
0x18001bde7  mov     r9d, 80090029h; char *
0x18001bded  mov     qword ptr [rsp+38h+var_18], rax; int
0x18001bdf2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001bdf9  mov     edx, 84h; void *
0x18001bdfe  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001be03  xor     al, al
0x18001be05  add     rsp, 38h
0x18001be09  retn
0x18001be0a  mov     al, 1
0x18001be0c  jmp     short loc_18001BE05
```
