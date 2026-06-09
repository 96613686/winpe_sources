# SspLogNTLMFallbackToWeakNtowf

- ea: `0x1800517d4`
- end: `0x18005193b`
- name: `SspLogNTLMFallbackToWeakNtowf`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800132c0`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x1800517d4`
- `0x18006d010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180051830`
- `ntdll!EtwEventEnabled` at `0x180051830`
- `ntdll!EtwEventWrite` at `0x1800518d9`
- `ntdll!EtwEventWrite` at `0x1800518d9`

## pseudocode

```c
__int64 __fastcall SspLogNTLMFallbackToWeakNtowf(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int128 v7; // [rsp+20h] [rbp-50h] BYREF
  __int128 v8; // [rsp+30h] [rbp-40h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-30h]
  __int128 v10; // [rsp+48h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-18h]

  v11 = 0;
  v9 = 0;
  v10 = 0;
  v7 = 0;
  v8 = 0;
  result = SspInitEtwLogHandle();
  if ( (int)result >= 0
    && (result = EtwEventEnabled(MsvEtwLogHandle, NTLMAuthFallbackToWeakNtowf), (_BYTE)result)
    && (result = NtLmDuplicateUnicodeString(&v7, a1), (int)result >= 0)
    && (result = NtLmDuplicateUnicodeString(&v8, a2), (int)result >= 0) )
  {
    v5 = *((_QWORD *)&v7 + 1);
    if ( *((_QWORD *)&v7 + 1) && (_WORD)v7 )
    {
      v9 = (const wchar_t *)*((_QWORD *)&v7 + 1);
      *(_QWORD *)&v10 = (unsigned int)(unsigned __int16)v7 + 2;
    }
    else
    {
      v9 = L"(NULL)";
      *(_QWORD *)&v10 = 14;
    }
    v6 = *((_QWORD *)&v8 + 1);
    if ( *((_QWORD *)&v8 + 1) && (_WORD)v8 )
    {
      *((_QWORD *)&v10 + 1) = *((_QWORD *)&v8 + 1);
      v11 = (unsigned int)(unsigned __int16)v8 + 2;
    }
    else
    {
      *((_QWORD *)&v10 + 1) = L"(NULL)";
      v11 = 14;
    }
    result = EtwEventWrite(MsvEtwLogHandle, NTLMAuthFallbackToWeakNtowf, 2);
  }
  else
  {
    v5 = *((_QWORD *)&v7 + 1);
    v6 = *((_QWORD *)&v8 + 1);
  }
  if ( v5 )
    result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v5);
  if ( v6 )
    return ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v6);
  return result;
}

```

## disassembly

```asm
0x1800517d4  mov     [rsp-18h+arg_10], rbx
0x1800517d9  push    rbp
0x1800517da  push    rsi
0x1800517db  push    rdi
0x1800517dc  mov     rbp, rsp
0x1800517df  sub     rsp, 70h
0x1800517e3  mov     rax, cs:__security_cookie
0x1800517ea  xor     rax, rsp
0x1800517ed  mov     [rbp+var_10], rax
0x1800517f1  xorps   xmm0, xmm0
0x1800517f4  xor     eax, eax
0x1800517f6  xorps   xmm1, xmm1
0x1800517f9  mov     [rbp+var_18], rax
0x1800517fd  xor     esi, esi
0x1800517ff  mov     rdi, rdx
0x180051802  mov     [rbp+var_30], rsi
0x180051806  mov     rbx, rcx
0x180051809  movups  [rbp+var_28], xmm0
0x18005180d  movups  [rbp+var_50], xmm0
0x180051811  movups  [rbp+var_40], xmm1
0x180051815  call    SspInitEtwLogHandle
0x18005181a  test    eax, eax
0x18005181c  js      loc_1800518E1
0x180051822  mov     rcx, cs:MsvEtwLogHandle
0x180051829  lea     rdx, NTLMAuthFallbackToWeakNtowf
0x180051830  call    cs:__imp_EtwEventEnabled
0x180051836  test    al, al
0x180051838  jz      loc_1800518E1
0x18005183e  mov     rdx, rbx
0x180051841  lea     rcx, [rbp+var_50]
0x180051845  call    NtLmDuplicateUnicodeString
0x18005184a  test    eax, eax
0x18005184c  js      loc_1800518E1
0x180051852  mov     rdx, rdi
0x180051855  lea     rcx, [rbp+var_40]
0x180051859  call    NtLmDuplicateUnicodeString
0x18005185e  test    eax, eax
0x180051860  js      short loc_1800518E1
0x180051862  mov     rdi, qword ptr [rbp+var_50+8]
0x180051866  lea     rcx, aNull; "(NULL)"
0x18005186d  lea     r8d, [rsi+2]
0x180051871  test    rdi, rdi
0x180051874  jz      short loc_18005188E
0x180051876  movzx   eax, word ptr [rbp+var_50]
0x18005187a  test    ax, ax
0x18005187d  jz      short loc_18005188E
0x18005187f  add     eax, r8d
0x180051882  mov     [rbp+var_30], rdi
0x180051886  mov     dword ptr [rbp+var_28], eax
0x180051889  mov     dword ptr [rbp+var_28+4], esi
0x18005188c  jmp     short loc_18005189A
0x18005188e  mov     [rbp+var_30], rcx
0x180051892  mov     qword ptr [rbp+var_28], 0Eh
0x18005189a  mov     rbx, qword ptr [rbp+var_40+8]
0x18005189e  test    rbx, rbx
0x1800518a1  jz      short loc_1800518BB
0x1800518a3  movzx   eax, word ptr [rbp+var_40]
0x1800518a7  test    ax, ax
0x1800518aa  jz      short loc_1800518BB
0x1800518ac  add     eax, r8d
0x1800518af  mov     qword ptr [rbp+var_28+8], rbx
0x1800518b3  mov     dword ptr [rbp+var_18], eax
0x1800518b6  mov     dword ptr [rbp+var_18+4], esi
0x1800518b9  jmp     short loc_1800518C7
0x1800518bb  mov     qword ptr [rbp+var_28+8], rcx
0x1800518bf  mov     [rbp+var_18], 0Eh
0x1800518c7  mov     rcx, cs:MsvEtwLogHandle
0x1800518ce  lea     r9, [rbp+var_30]
0x1800518d2  lea     rdx, NTLMAuthFallbackToWeakNtowf
0x1800518d9  call    cs:__imp_EtwEventWrite
0x1800518df  jmp     short loc_1800518E9
0x1800518e1  mov     rdi, qword ptr [rbp+var_50+8]
0x1800518e5  mov     rbx, qword ptr [rbp+var_40+8]
0x1800518e9  test    rdi, rdi
0x1800518ec  jz      short loc_180051904
0x1800518ee  mov     rax, cs:LsaFunctions
0x1800518f5  mov     rcx, rdi
0x1800518f8  mov     rax, [rax+188h]
0x1800518ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051904  test    rbx, rbx
0x180051907  jz      short loc_18005191F
0x180051909  mov     rax, cs:LsaFunctions
0x180051910  mov     rcx, rbx
0x180051913  mov     rax, [rax+188h]
0x18005191a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005191f  mov     rcx, [rbp+var_10]
0x180051923  xor     rcx, rsp; StackCookie
0x180051926  call    __security_check_cookie
0x18005192b  mov     rbx, [rsp+70h+arg_10]
0x180051933  add     rsp, 70h
0x180051937  pop     rdi
0x180051938  pop     rsi
0x180051939  pop     rbp
0x18005193a  retn
```
