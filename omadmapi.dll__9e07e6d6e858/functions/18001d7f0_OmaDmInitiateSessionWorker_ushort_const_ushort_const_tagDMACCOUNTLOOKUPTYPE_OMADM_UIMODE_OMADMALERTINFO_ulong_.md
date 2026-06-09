# OmaDmInitiateSessionWorker(ushort const *,ushort const *,tagDMACCOUNTLOOKUPTYPE,OMADM_UIMODE,OMADMALERTINFO *,ulong,uchar *,ulong,PushRouterSubmitOrigin,int,int)

- ea: `0x18001d7f0`
- end: `0x18001d9b9`
- name: `?OmaDmInitiateSessionWorker@@YAJPEBG0W4tagDMACCOUNTLOOKUPTYPE@@W4OMADM_UIMODE@@PEAUOMADMALERTINFO@@KPEAEKW4PushRouterSubmitOrigin@@HH@Z`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180018cf0`
- `0x180018ea0`
- `0x180019060`
- `0x180019250`

## callees

- `0x180003db8`
- `0x18000f47c`
- `0x180019570`
- `0x18001d7f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d999`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d988`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d999`
- `DMCmnUtils!CopyString` at `0x18001d8ec`
- `DMCmnUtils!CopyString` at `0x18001d8ec`

## pseudocode

```c
__int64 __fastcall OmaDmInitiateSessionWorker(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        void *a7,
        size_t Size,
        unsigned int a9,
        int a10,
        int a11)
{
  _WORD *v11; // rdi
  BOOL v12; // r12d
  unsigned int v16; // r14d
  __int64 v17; // rbx
  signed int AccountIDFromLookupID; // ebx
  unsigned __int64 v19; // rdx
  _WORD *v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // rcx
  HLOCAL v24[11]; // [rsp+60h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+10h] BYREF

  v11 = a7;
  hMem = 0;
  v24[0] = 0;
  v12 = a7 == 0;
  if ( !a2 )
    goto LABEL_23;
  v16 = a6;
  v17 = a5;
  if ( a6 )
  {
    if ( !a5 )
      goto LABEL_23;
  }
  if ( a4 > 4 )
    goto LABEL_23;
  if ( a7 )
    memset_0(a7, 0, (unsigned int)Size);
  AccountIDFromLookupID = OmaDmInitiateSession_Impl(a1, v17, v16, v12, (__int64)&hMem, a9, a10, a11);
  if ( AccountIDFromLookupID >= 0 )
  {
    if ( a3 )
    {
      if ( a3 != 1 )
        goto LABEL_23;
      AccountIDFromLookupID = CopyString(a2, 0xFFFFFFFF, (unsigned __int16 **)v24);
      if ( AccountIDFromLookupID >= 0 )
      {
LABEL_14:
        AccountIDFromLookupID = 0;
        if ( !v11 )
          goto LABEL_24;
        v19 = (unsigned __int64)(unsigned int)Size >> 1;
        if ( v19 )
        {
          v20 = hMem;
          v21 = 2147483646;
          do
          {
            if ( !v21 )
              break;
            if ( !*v20 )
              break;
            *v11++ = *v20++;
            --v21;
            --v19;
          }
          while ( v19 );
          v22 = v11 - 1;
          AccountIDFromLookupID = v19 == 0 ? 0x8007007A : 0;
          if ( v19 )
            v22 = v11;
          *v22 = 0;
          goto LABEL_24;
        }
LABEL_23:
        AccountIDFromLookupID = -2147024809;
        goto LABEL_24;
      }
    }
    else
    {
      AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID((__int16 *)a2, 0, (unsigned __int16 **)v24);
    }
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_24;
    goto LABEL_14;
  }
LABEL_24:
  LocalFree(hMem);
  LocalFree(v24[0]);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x18001d7f0  mov     rax, rsp
0x18001d7f3  push    rbx
0x18001d7f4  push    rbp
0x18001d7f5  push    rsi
0x18001d7f6  push    rdi
0x18001d7f7  push    r12
0x18001d7f9  push    r13
0x18001d7fb  push    r14
0x18001d7fd  push    r15
0x18001d7ff  sub     rsp, 78h
0x18001d803  mov     rdi, [rsp+0B8h+arg_30]
0x18001d80b  xor     r12d, r12d
0x18001d80e  test    rdi, rdi
0x18001d811  mov     qword ptr [rax+10h], 0
0x18001d819  mov     r15d, r9d
0x18001d81c  mov     qword ptr [rax-58h], 0
0x18001d824  setz    r12b
0x18001d828  mov     esi, r8d
0x18001d82b  mov     rbp, rdx
0x18001d82e  mov     r13, rcx
0x18001d831  test    rdx, rdx
0x18001d834  jz      loc_18001D97B
0x18001d83a  mov     r14d, [rsp+0B8h+arg_28]
0x18001d842  mov     rbx, [rsp+0B8h+arg_20]
0x18001d84a  test    r14d, r14d
0x18001d84d  jz      short loc_18001D858
0x18001d84f  test    rbx, rbx
0x18001d852  jz      loc_18001D97B
0x18001d858  cmp     r15d, 4
0x18001d85c  ja      loc_18001D97B
0x18001d862  test    rdi, rdi
0x18001d865  jz      short loc_18001D879
0x18001d867  mov     r8d, dword ptr [rsp+0B8h+Size]; Size
0x18001d86f  xor     edx, edx; Val
0x18001d871  mov     rcx, rdi; void *
0x18001d874  call    memset_0
0x18001d879  mov     eax, [rsp+0B8h+arg_50]
0x18001d880  mov     r9d, r15d
0x18001d883  mov     [rsp+0B8h+var_68], eax
0x18001d887  mov     r8d, esi
0x18001d88a  mov     eax, [rsp+0B8h+arg_48]
0x18001d891  mov     rdx, rbp
0x18001d894  mov     [rsp+0B8h+var_70], eax
0x18001d898  mov     rcx, r13
0x18001d89b  mov     eax, [rsp+0B8h+arg_40]
0x18001d8a2  mov     [rsp+0B8h+var_78], eax
0x18001d8a6  lea     rax, [rsp+0B8h+hMem]
0x18001d8ae  mov     [rsp+0B8h+var_80], rax
0x18001d8b3  mov     [rsp+0B8h+var_88], r12d
0x18001d8b8  mov     [rsp+0B8h+var_90], r14d
0x18001d8bd  mov     [rsp+0B8h+var_98], rbx
0x18001d8c2  call    OmaDmInitiateSession_Impl
0x18001d8c7  xor     r14d, r14d
0x18001d8ca  mov     ebx, eax
0x18001d8cc  test    eax, eax
0x18001d8ce  js      loc_18001D980
0x18001d8d4  test    esi, esi
0x18001d8d6  jz      short loc_18001D900
0x18001d8d8  cmp     esi, 1
0x18001d8db  jnz     loc_18001D97B
0x18001d8e1  lea     r8, [rsp+0B8h+var_58]
0x18001d8e6  or      edx, 0FFFFFFFFh
0x18001d8e9  mov     rcx, rbp
0x18001d8ec  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001d8f3  nop     dword ptr [rax+rax+00h]
0x18001d8f8  mov     ebx, eax
0x18001d8fa  test    eax, eax
0x18001d8fc  js      short loc_18001D911
0x18001d8fe  jmp     short loc_18001D915
0x18001d900  lea     r8, [rsp+0B8h+var_58]
0x18001d905  xor     edx, edx
0x18001d907  mov     rcx, rbp
0x18001d90a  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18001d90f  mov     ebx, eax
0x18001d911  test    ebx, ebx
0x18001d913  js      short loc_18001D980
0x18001d915  mov     ebx, r14d
0x18001d918  test    rdi, rdi
0x18001d91b  jz      short loc_18001D980
0x18001d91d  mov     edx, dword ptr [rsp+0B8h+Size]
0x18001d924  shr     rdx, 1
0x18001d927  jz      short loc_18001D97B
0x18001d929  mov     rcx, [rsp+0B8h+hMem]
0x18001d931  mov     eax, 7FFFFFFEh
0x18001d936  test    rax, rax
0x18001d939  jz      short loc_18001D95A
0x18001d93b  movzx   r8d, word ptr [rcx]
0x18001d93f  test    r8w, r8w
0x18001d943  jz      short loc_18001D95A
0x18001d945  mov     [rdi], r8w
0x18001d949  add     rcx, 2
0x18001d94d  add     rdi, 2
0x18001d951  dec     rax
0x18001d954  sub     rdx, 1
0x18001d958  jnz     short loc_18001D936
0x18001d95a  mov     rax, rdx
0x18001d95d  lea     rcx, [rdi-2]
0x18001d961  neg     rax
0x18001d964  sbb     ebx, ebx
0x18001d966  not     ebx
0x18001d968  and     ebx, 8007007Ah
0x18001d96e  test    rdx, rdx
0x18001d971  cmovnz  rcx, rdi
0x18001d975  mov     [rcx], r14w
0x18001d979  jmp     short loc_18001D980
0x18001d97b  mov     ebx, 80070057h
0x18001d980  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18001d988  call    cs:__imp_LocalFree
0x18001d98f  nop     dword ptr [rax+rax+00h]
0x18001d994  mov     rcx, [rsp+0B8h+var_58]; hMem
0x18001d999  call    cs:__imp_LocalFree
0x18001d9a0  nop     dword ptr [rax+rax+00h]
0x18001d9a5  mov     eax, ebx
0x18001d9a7  add     rsp, 78h
0x18001d9ab  pop     r15
0x18001d9ad  pop     r14
0x18001d9af  pop     r13
0x18001d9b1  pop     r12
0x18001d9b3  pop     rdi
0x18001d9b4  pop     rsi
0x18001d9b5  pop     rbp
0x18001d9b6  pop     rbx
0x18001d9b7  retn
```
