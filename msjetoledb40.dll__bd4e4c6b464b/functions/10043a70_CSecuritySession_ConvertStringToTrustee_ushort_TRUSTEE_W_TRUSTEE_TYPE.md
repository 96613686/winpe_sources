# CSecuritySession::ConvertStringToTrustee(ushort *,_TRUSTEE_W * *,_TRUSTEE_TYPE)

- ea: `0x10043a70`
- end: `0x10043b77`
- name: `?ConvertStringToTrustee@CSecuritySession@@QAEJPAGPAPAU_TRUSTEE_W@@W4_TRUSTEE_TYPE@@@Z`
- size: `263`
- prototype: `int __thiscall(CSecuritySession *__hidden this, unsigned __int16 *, struct _TRUSTEE_W **, enum _TRUSTEE_TYPE)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100429a0`
- `0x100434f0`

## callees

- `0x1000ba50`
- `0x1000d4a0`
- `0x1001c6d0`
- `0x10043a70`

## pseudocode

```c
int __userpurge CSecuritySession::ConvertStringToTrustee@<eax>(
        const unsigned __int16 *a1@<ebx>,
        unsigned __int16 *a2,
        struct _TRUSTEE_W **a3,
        enum _TRUSTEE_TYPE a4)
{
  struct _TRUSTEE_W *v5; // eax
  int result; // eax
  unsigned __int16 *ptstrName; // ecx
  unsigned int v8; // [esp+0h] [ebp-Ch]
  unsigned __int16 *v9; // [esp+8h] [ebp-4h]

  v5 = (struct _TRUSTEE_W *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                              *(_DWORD *)(*(_DWORD *)Sys + 12),
                              Sys,
                              20);
  *a3 = v5;
  if ( !v5 )
    return -2147024882;
  v5->ptstrName = 0;
  if ( !a2 )
    goto LABEL_11;
  v9 = (unsigned __int16 *)(2 * wcslen(a2) + 2);
  (*a3)->ptstrName = (LPWCH)(*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                              *(_DWORD *)(*(_DWORD *)Sys + 12),
                              Sys,
                              v9);
  ptstrName = (*a3)->ptstrName;
  if ( ptstrName )
  {
    WCSCPY(a2, ptstrName, v9, a1, v8);
LABEL_11:
    result = 0;
    (*a3)->pMultipleTrustee = 0;
    (*a3)->MultipleTrusteeOperation = NO_MULTIPLE_TRUSTEE;
    (*a3)->TrusteeForm = TRUSTEE_IS_NAME;
    (*a3)->TrusteeType = TRUSTEE_IS_USER;
    return result;
  }
  if ( *a3 )
  {
    if ( Sys )
      (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(*(_DWORD *)(*(_DWORD *)Sys + 20), Sys, *a3);
    *a3 = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x10043a70  mov     edi, edi
0x10043a72  push    ebp
0x10043a73  mov     ebp, esp
0x10043a75  push    ecx
0x10043a76  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10043a7c  push    esi
0x10043a7d  push    edi; unsigned int
0x10043a7e  push    14h
0x10043a80  mov     eax, [ecx]
0x10043a82  push    ecx
0x10043a83  mov     esi, [eax+0Ch]
0x10043a86  mov     ecx, esi
0x10043a88  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10043a8e  call    esi
0x10043a90  mov     edi, [ebp+arg_4]
0x10043a93  mov     [edi], eax
0x10043a95  test    eax, eax
0x10043a97  jnz     short loc_10043AA6
0x10043a99  pop     edi
0x10043a9a  mov     eax, 8007000Eh
0x10043a9f  pop     esi
0x10043aa0  mov     esp, ebp
0x10043aa2  pop     ebp
0x10043aa3  retn    0Ch
0x10043aa6  push    ebx; unsigned __int16 *
0x10043aa7  mov     ebx, [ebp+arg_0]
0x10043aaa  mov     dword ptr [eax+10h], 0
0x10043ab1  test    ebx, ebx
0x10043ab3  jz      loc_10043B49
0x10043ab9  mov     ecx, ebx
0x10043abb  lea     edx, [ecx+2]
0x10043abe  mov     edi, edi
0x10043ac0  mov     ax, [ecx]
0x10043ac3  add     ecx, 2
0x10043ac6  test    ax, ax
0x10043ac9  jnz     short loc_10043AC0
0x10043acb  sub     ecx, edx
0x10043acd  sar     ecx, 1
0x10043acf  lea     edx, ds:2[ecx*2]
0x10043ad6  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10043adc  push    edx
0x10043add  push    ecx
0x10043ade  mov     [ebp+var_4], edx
0x10043ae1  mov     eax, [ecx]
0x10043ae3  mov     esi, [eax+0Ch]
0x10043ae6  mov     ecx, esi
0x10043ae8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10043aee  call    esi
0x10043af0  mov     ecx, eax
0x10043af2  mov     eax, [edi]
0x10043af4  mov     [eax+10h], ecx
0x10043af7  mov     eax, [edi]
0x10043af9  mov     ecx, [eax+10h]; void *
0x10043afc  test    ecx, ecx
0x10043afe  jnz     short loc_10043B3F
0x10043b00  test    eax, eax
0x10043b02  jz      short loc_10043B31
0x10043b04  mov     eax, ecx
0x10043b06  test    eax, eax
0x10043b08  jz      short loc_10043B10
0x10043b0a  push    eax
0x10043b0b  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10043b10  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x10043b15  test    eax, eax
0x10043b17  jz      short loc_10043B2B
0x10043b19  mov     ecx, [eax]
0x10043b1b  push    dword ptr [edi]
0x10043b1d  push    eax
0x10043b1e  mov     esi, [ecx+14h]
0x10043b21  mov     ecx, esi
0x10043b23  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10043b29  call    esi
0x10043b2b  mov     dword ptr [edi], 0
0x10043b31  pop     ebx
0x10043b32  pop     edi
0x10043b33  mov     eax, 8007000Eh
0x10043b38  pop     esi
0x10043b39  mov     esp, ebp
0x10043b3b  pop     ebp
0x10043b3c  retn    0Ch
0x10043b3f  push    [ebp+var_4]; unsigned __int16 *
0x10043b42  mov     edx, ebx
0x10043b44  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x10043b49  mov     ecx, [edi]
0x10043b4b  xor     eax, eax
0x10043b4d  pop     ebx
0x10043b4e  mov     dword ptr [ecx], 0
0x10043b54  mov     ecx, [edi]
0x10043b56  mov     dword ptr [ecx+4], 0
0x10043b5d  mov     ecx, [edi]
0x10043b5f  mov     dword ptr [ecx+8], 1
0x10043b66  mov     ecx, [edi]
0x10043b68  pop     edi
0x10043b69  pop     esi
0x10043b6a  mov     dword ptr [ecx+0Ch], 1
0x10043b71  mov     esp, ebp
0x10043b73  pop     ebp
0x10043b74  retn    0Ch
```
