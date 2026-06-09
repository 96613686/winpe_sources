# SipProvider::GetCryptHasher(SipCryptProvider const *,ulong,CryptHash * *)

- ea: `0x180003d50`
- end: `0x180003dcc`
- name: `?GetCryptHasher@SipProvider@@CAKPEBVSipCryptProvider@@KPEAPEAVCryptHash@@@Z`
- size: `124`
- prototype: `static unsigned int(const struct SipCryptProvider *, unsigned int, struct CryptHash **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003dd4`
- `0x180003ed8`

## callees

- `0x180001008`
- `0x180001014`
- `0x180003348`
- `0x180003d50`
- `0x180004574`

## pseudocode

```c
__int64 __fastcall SipProvider::GetCryptHasher(HCRYPTPROV *a1, ALG_ID a2, HCRYPTHASH **a3)
{
  DWORD inited; // edi
  HCRYPTHASH *v7; // rax
  HCRYPTHASH *v8; // rbx

  if ( a1 && a3 )
  {
    inited = 8;
    *a3 = 0;
    v7 = (HCRYPTHASH *)operator new(8u);
    v8 = v7;
    if ( v7 )
    {
      *v7 = 0;
      inited = CryptHash::InitHash(v7, *a1, a2);
      if ( inited )
      {
        CryptHash::~CryptHash(v8);
        operator delete(v8);
      }
      else
      {
        *a3 = v8;
      }
    }
  }
  else
  {
    return 87;
  }
  return inited;
}

```

## disassembly

```asm
0x180003d50  push    rbx
0x180003d52  push    rbp
0x180003d53  push    rsi
0x180003d54  push    rdi
0x180003d55  push    r14
0x180003d57  sub     rsp, 20h
0x180003d5b  mov     rsi, r8
0x180003d5e  mov     ebp, edx
0x180003d60  mov     r14, rcx
0x180003d63  test    rcx, rcx
0x180003d66  jz      short loc_180003DBA
0x180003d68  test    r8, r8
0x180003d6b  jz      short loc_180003DBA
0x180003d6d  mov     edi, 8
0x180003d72  mov     qword ptr [r8], 0
0x180003d79  mov     ecx, edi; Size
0x180003d7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003d80  mov     rbx, rax
0x180003d83  test    rax, rax
0x180003d86  jz      short loc_180003DBF
0x180003d88  mov     qword ptr [rax], 0
0x180003d8f  mov     r8d, ebp; Algid
0x180003d92  mov     rdx, [r14]; hProv
0x180003d95  mov     rcx, rax; phHash
0x180003d98  call    ?InitHash@CryptHash@@QEAAK_KI@Z; CryptHash::InitHash(unsigned __int64,uint)
0x180003d9d  mov     edi, eax
0x180003d9f  test    eax, eax
0x180003da1  jnz     short loc_180003DA8
0x180003da3  mov     [rsi], rbx
0x180003da6  jmp     short loc_180003DBF
0x180003da8  mov     rcx, rbx; this
0x180003dab  call    ??1CryptHash@@QEAA@XZ; CryptHash::~CryptHash(void)
0x180003db0  mov     rcx, rbx; Block
0x180003db3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003db8  jmp     short loc_180003DBF
0x180003dba  mov     edi, 57h ; 'W'
0x180003dbf  mov     eax, edi
0x180003dc1  add     rsp, 20h
0x180003dc5  pop     r14
0x180003dc7  pop     rdi
0x180003dc8  pop     rsi
0x180003dc9  pop     rbp
0x180003dca  pop     rbx
0x180003dcb  retn
```
