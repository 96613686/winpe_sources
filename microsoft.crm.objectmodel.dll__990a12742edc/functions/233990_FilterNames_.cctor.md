# FilterNames::.cctor

- ea: `0x233990`
- end: `0x233a4a`
- name: `FilterNames::.cctor`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update`

## string_xrefs

- `0x233998`: `Create`
- `0x2339b8`: `Update`
- `0x2339a0`: `Delete`
- `0x2339f6`: `GrantAccess`
- `0x2339fe`: `ModifyAccess`
- `0x233a06`: `RetrievePrincipalAccess`
- `0x233a16`: `RetrieveSharedPrincipalsAndAccess`
- `0x233a0e`: `RevokeAccess`

## pseudocode

```c

```

## disassembly

```asm
0x233990  ldc.i4.5
0x233991  newarr   [mscorlib]System.String
0x233996  dup
0x233997  ldc.i4.0
0x233998  ldstr    aCreate// "Create"
0x23399d  stelem.ref
0x23399e  dup
0x23399f  ldc.i4.1
0x2339a0  ldstr    aDelete// "Delete"
0x2339a5  stelem.ref
0x2339a6  dup
0x2339a7  ldc.i4.2
0x2339a8  ldstr    aRetrieve// "Retrieve"
0x2339ad  stelem.ref
0x2339ae  dup
0x2339af  ldc.i4.3
0x2339b0  ldstr    aRetrievemultip// "RetrieveMultiple"
0x2339b5  stelem.ref
0x2339b6  dup
0x2339b7  ldc.i4.4
0x2339b8  ldstr    aUpdate// "Update"
0x2339bd  stelem.ref
0x2339be  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::CommonFilterNames
0x2339c3  ldc.i4.3
0x2339c4  newarr   [mscorlib]System.String
0x2339c9  dup
0x2339ca  ldc.i4.0
0x2339cb  ldstr    aSetstate// "SetState"
0x2339d0  stelem.ref
0x2339d1  dup
0x2339d2  ldc.i4.1
0x2339d3  ldstr    aIsvalidstatetr// "IsValidStateTransition"
0x2339d8  stelem.ref
0x2339d9  dup
0x2339da  ldc.i4.2
0x2339db  ldstr    aSetstatedynami// "SetStateDynamicEntity"
0x2339e0  stelem.ref
0x2339e1  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::NativeEntityFilterNames
0x2339e6  ldc.i4.6
0x2339e7  newarr   [mscorlib]System.String
0x2339ec  dup
0x2339ed  ldc.i4.0
0x2339ee  ldstr    aAssign// "Assign"
0x2339f3  stelem.ref
0x2339f4  dup
0x2339f5  ldc.i4.1
0x2339f6  ldstr    aGrantaccess// "GrantAccess"
0x2339fb  stelem.ref
0x2339fc  dup
0x2339fd  ldc.i4.2
0x2339fe  ldstr    aModifyaccess// "ModifyAccess"
0x233a03  stelem.ref
0x233a04  dup
0x233a05  ldc.i4.3
0x233a06  ldstr    aRetrieveprinci// "RetrievePrincipalAccess"
0x233a0b  stelem.ref
0x233a0c  dup
0x233a0d  ldc.i4.4
0x233a0e  ldstr    aRevokeaccess// "RevokeAccess"
0x233a13  stelem.ref
0x233a14  dup
0x233a15  ldc.i4.5
0x233a16  ldstr    aRetrieveshared// "RetrieveSharedPrincipalsAndAccess"
0x233a1b  stelem.ref
0x233a1c  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::UserOwnedFilterNames
0x233a21  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::CommonFilterNames
0x233a26  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::NativeEntityFilterNames
0x233a2b  call     T0x2B0000F6
0x233a30  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::OrgOwnedNativeEntityFilterNames
0x233a35  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::OrgOwnedNativeEntityFilterNames
0x233a3a  ldsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::UserOwnedFilterNames
0x233a3f  call     T0x2B0000F6
0x233a44  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<string> FilterNames::UserOwnedEntityFilterNames
0x233a49  ret
```
