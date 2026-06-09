# StrongNameTokenFromPublicKey

- ea: `0x18002ee44`
- end: `0x18002eef0`
- name: `StrongNameTokenFromPublicKey`
- size: `172`
- prototype: `BOOLEAN __stdcall(BYTE *pbPublicKeyBlob, ULONG cbPublicKeyBlob, BYTE **ppbStrongNameToken, ULONG *pcbStrongNameToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180028670`

## callees

- `0x180028d98`
- `0x180029490`
- `0x18002a2e4`
- `0x18002ee44`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002eea3`
- `KERNEL32!GetProcAddress` at `0x18002eea3`

## string_xrefs

- `0x18002ee9c`: `StrongNameTokenFromPublicKey`

## pseudocode

```c
BOOLEAN __stdcall StrongNameTokenFromPublicKey(
        BYTE *pbPublicKeyBlob,
        ULONG cbPublicKeyBlob,
        BYTE **ppbStrongNameToken,
        ULONG *pcbStrongNameToken)
{
  unsigned __int8 (*ProcAddress)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *); // rax
  StrongNameTokenFromPublicKeyCache *v10; // rcx
  BOOLEAN v11; // bl
  int v12; // [rsp+28h] [rbp-40h]
  HMODULE hModule; // [rsp+30h] [rbp-38h] BYREF

  if ( StrongNameTokenFromPublicKeyCache::FindEntry(
         (StrongNameTokenFromPublicKeyCache *)pbPublicKeyBlob,
         pbPublicKeyBlob,
         cbPublicKeyBlob,
         ppbStrongNameToken,
         pcbStrongNameToken) )
  {
    return 1;
  }
  ProcAddress = g_StrongNameTokenFromPublicKey;
  if ( !g_StrongNameTokenFromPublicKey )
  {
    hModule = 0;
    if ( (int)GetRealStrongNameDll(&hModule) < 0 )
      return 0;
    ProcAddress = (unsigned __int8 (*)(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *))GetProcAddress(hModule, "StrongNameTokenFromPublicKey");
    g_StrongNameTokenFromPublicKey = ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  v11 = ((__int64 (__fastcall *)(BYTE *, _QWORD, BYTE **, ULONG *))ProcAddress)(
          pbPublicKeyBlob,
          cbPublicKeyBlob,
          ppbStrongNameToken,
          pcbStrongNameToken);
  if ( v11 )
    StrongNameTokenFromPublicKeyCache::AddEntry(
      v10,
      pbPublicKeyBlob,
      cbPublicKeyBlob,
      ppbStrongNameToken,
      pcbStrongNameToken,
      v12);
  return v11;
}

```

## disassembly

```asm
0x18002ee44  push    rbx
0x18002ee46  push    rbp
0x18002ee47  push    rsi
0x18002ee48  push    rdi
0x18002ee49  push    r14
0x18002ee4b  sub     rsp, 40h
0x18002ee4f  mov     rdi, r9
0x18002ee52  mov     [rsp+68h+var_48], r9; unsigned int *
0x18002ee57  mov     r9, r8; unsigned __int8 **
0x18002ee5a  mov     rsi, r8
0x18002ee5d  mov     r8d, edx; unsigned int
0x18002ee60  mov     ebp, edx
0x18002ee62  mov     rdx, rcx; unsigned __int8 *
0x18002ee65  mov     r14, rcx
0x18002ee68  call    ?FindEntry@StrongNameTokenFromPublicKeyCache@@QEAAHPEAEKPEAPEAEPEAK@Z; StrongNameTokenFromPublicKeyCache::FindEntry(uchar *,ulong,uchar * *,ulong *)
0x18002ee6d  test    eax, eax
0x18002ee6f  jz      short loc_18002EE78
0x18002ee71  mov     eax, 1
0x18002ee76  jmp     short loc_18002EEE5
0x18002ee78  mov     rax, cs:?g_StrongNameTokenFromPublicKey@@3P6AEPEAEKPEAPEAEPEAK@ZEA; uchar (*g_StrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x18002ee7f  test    rax, rax
0x18002ee82  jnz     short loc_18002EEB5
0x18002ee84  lea     rcx, [rsp+68h+hModule]; HINSTANCE *
0x18002ee89  mov     [rsp+68h+hModule], rax
0x18002ee8e  call    ?GetRealStrongNameDll@@YAJPEAPEAUHINSTANCE__@@@Z; GetRealStrongNameDll(HINSTANCE__ * *)
0x18002ee93  test    eax, eax
0x18002ee95  js      short loc_18002EEE1
0x18002ee97  mov     rcx, [rsp+68h+hModule]; hModule
0x18002ee9c  lea     rdx, aStrongnametoke_3; "StrongNameTokenFromPublicKey"
0x18002eea3  call    cs:__imp_GetProcAddress
0x18002eea9  mov     cs:?g_StrongNameTokenFromPublicKey@@3P6AEPEAEKPEAPEAEPEAK@ZEA, rax; uchar (*g_StrongNameTokenFromPublicKey)(uchar *,ulong,uchar * *,ulong *)
0x18002eeb0  test    rax, rax
0x18002eeb3  jz      short loc_18002EEE1
0x18002eeb5  mov     r9, rdi
0x18002eeb8  mov     r8, rsi
0x18002eebb  mov     edx, ebp
0x18002eebd  mov     rcx, r14
0x18002eec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eec5  movzx   ebx, al
0x18002eec8  test    al, al
0x18002eeca  jz      short loc_18002EEE3
0x18002eecc  mov     r9, rsi; unsigned __int8 **
0x18002eecf  mov     [rsp+68h+var_48], rdi; unsigned int *
0x18002eed4  mov     r8d, ebp; unsigned int
0x18002eed7  mov     rdx, r14; unsigned __int8 *
0x18002eeda  call    ?AddEntry@StrongNameTokenFromPublicKeyCache@@QEAAXPEAEKPEAPEAEPEAKH@Z; StrongNameTokenFromPublicKeyCache::AddEntry(uchar *,ulong,uchar * *,ulong *,int)
0x18002eedf  jmp     short loc_18002EEE3
0x18002eee1  xor     ebx, ebx
0x18002eee3  mov     eax, ebx
0x18002eee5  add     rsp, 40h
0x18002eee9  pop     r14
0x18002eeeb  pop     rdi
0x18002eeec  pop     rsi
0x18002eeed  pop     rbp
0x18002eeee  pop     rbx
0x18002eeef  retn
```
