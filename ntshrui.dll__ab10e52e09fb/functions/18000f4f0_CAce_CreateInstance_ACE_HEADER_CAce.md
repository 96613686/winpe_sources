# CAce::CreateInstance(_ACE_HEADER *,CAce * *)

- ea: `0x18000f4f0`
- end: `0x18000f70f`
- name: `?CreateInstance@CAce@@SAJPEAU_ACE_HEADER@@PEAPEAV1@@Z`
- size: `543`
- prototype: `__int64 __fastcall(struct _ACE_HEADER *, struct CAce **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024014`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000f4b0`
- `0x18000f4f0`
- `0x1800259bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f594`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000f594`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f5fb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000f5fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f5cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f6ca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f5cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000f6ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f5e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f6bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f6bf`
- `ntdll!RtlMapGenericMask` at `0x18000f63e`
- `ntdll!RtlMapGenericMask` at `0x18000f63e`

## pseudocode

```c
__int64 __fastcall CAce::CreateInstance(struct _ACE_HEADER *a1, DWORD **a2)
{
  DWORD *v4; // rax
  unsigned int v5; // edx
  DWORD *v6; // rbx
  struct _ACE_HEADER *v7; // rsi
  BYTE AceType; // r12
  struct _ACE_HEADER *v9; // rcx
  struct _ACE_HEADER v10; // eax
  int Error; // edi
  __int64 result; // rax
  DWORD v13; // r13d
  HLOCAL v14; // rax
  void *v15; // rbp
  char v16; // cl
  unsigned int v17; // eax
  DWORD LengthSid; // eax
  BYTE AceFlags; // [rsp+88h] [rbp+10h]
  WORD AceSize; // [rsp+90h] [rbp+18h]
  struct _ACE_HEADER v21; // [rsp+98h] [rbp+20h]

  *a2 = 0;
  v4 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v6 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = 0x80000;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    if ( !a1 )
    {
      Error = -2147024809;
LABEL_19:
      CAce::`scalar deleting destructor'((CAce *)v6, v5);
      return (unsigned int)Error;
    }
    v7 = a1 + 2;
    AceType = a1->AceType;
    if ( a1->AceType == 9 )
    {
      LengthSid = GetLengthSid(&a1[2]);
      Error = CAce::_Init(
                (CAce *)v6,
                &a1[2],
                *(_DWORD *)&a1[1],
                a1->AceFlags,
                a1->AceType,
                a1->AceSize,
                &v7->AceType + LengthSid);
    }
    else if ( a1 == (struct _ACE_HEADER *)-8LL )
    {
      Error = -2147024809;
    }
    else
    {
      v9 = a1 + 2;
      AceSize = a1->AceSize;
      AceFlags = a1->AceFlags;
      v10 = a1[1];
      Error = -2147024809;
      v21 = v10;
      if ( IsValidSid(v9) )
      {
        v13 = GetLengthSid(v7);
        Error = -2147024882;
        v14 = LocalAlloc(0x40u, v13);
        v15 = v14;
        if ( v14 )
        {
          if ( CopySid(v13, v14, v7) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v15);
              goto LABEL_6;
            }
          }
          *((_QWORD *)v6 + 1) = v15;
          *((_BYTE *)v6 + 1) = AceFlags;
          *((_WORD *)v6 + 1) = AceSize;
          v6[1] = (DWORD)v21;
          *(_BYTE *)v6 = AceType;
          RtlMapGenericMask(v6 + 1, (PGENERIC_MAPPING)&GenericMapping);
          v16 = *(_BYTE *)v6;
          v17 = 0x80000000;
          v6[7] = 0x80000000;
          if ( !v16 || v16 == 9 )
          {
            v17 = -2147483647;
            v6[7] = -2147483647;
          }
          if ( (*((_BYTE *)v6 + 1) & 0x10) != 0 )
            v6[7] = v17 | 0x20;
        }
      }
    }
LABEL_6:
    if ( Error >= 0 )
    {
      result = (unsigned int)Error;
      *a2 = v6;
      return result;
    }
    goto LABEL_19;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f4f0  push    rbx
0x18000f4f2  push    rsi
0x18000f4f3  push    rdi
0x18000f4f4  push    r15
0x18000f4f6  sub     rsp, 58h
0x18000f4fa  mov     r15, rdx
0x18000f4fd  mov     rdi, rcx
0x18000f500  xor     esi, esi
0x18000f502  mov     ecx, 20h ; ' '; unsigned __int64
0x18000f507  mov     [rdx], rsi
0x18000f50a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f511  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f516  mov     [rsp+78h+arg_8], rax
0x18000f51e  mov     rbx, rax
0x18000f521  test    rax, rax
0x18000f524  jz      loc_18000F69E
0x18000f52a  mov     [rsp+78h+var_38], r14
0x18000f52f  mov     qword ptr [rax], 80000h
0x18000f536  mov     [rax+8], rsi
0x18000f53a  mov     [rax+10h], rsi
0x18000f53e  mov     [rax+18h], rsi
0x18000f542  test    rdi, rdi
0x18000f545  jz      loc_18000F680
0x18000f54b  mov     [rsp+78h+var_28], r12
0x18000f550  lea     rsi, [rdi+8]
0x18000f554  movzx   r12d, byte ptr [rdi]
0x18000f558  cmp     r12b, 9
0x18000f55c  jz      loc_18000F6C7
0x18000f562  test    rsi, rsi
0x18000f565  jz      loc_18000F705
0x18000f56b  movzx   eax, word ptr [rdi+2]
0x18000f56f  mov     rcx, rsi; pSid
0x18000f572  mov     [rsp+78h+arg_10], ax
0x18000f57a  movzx   eax, byte ptr [rdi+1]
0x18000f57e  mov     byte ptr [rsp+78h+arg_8], al
0x18000f585  mov     eax, [rdi+4]
0x18000f588  mov     edi, 80070057h
0x18000f58d  mov     [rsp+78h+arg_18], eax
0x18000f594  call    cs:__imp_IsValidSid
0x18000f59a  test    eax, eax
0x18000f59c  jnz     short loc_18000F5BF
0x18000f59e  mov     r12, [rsp+78h+var_28]
0x18000f5a3  test    edi, edi
0x18000f5a5  js      loc_18000F685
0x18000f5ab  mov     r14, [rsp+78h+var_38]
0x18000f5b0  mov     eax, edi
0x18000f5b2  mov     [r15], rbx
0x18000f5b5  add     rsp, 58h
0x18000f5b9  pop     r15
0x18000f5bb  pop     rdi
0x18000f5bc  pop     rsi
0x18000f5bd  pop     rbx
0x18000f5be  retn
0x18000f5bf  mov     [rsp+78h+arg_0], rbp
0x18000f5c7  mov     rcx, rsi; pSid
0x18000f5ca  mov     [rsp+78h+var_30], r13
0x18000f5cf  call    cs:__imp_GetLengthSid
0x18000f5d5  mov     edx, eax; uBytes
0x18000f5d7  mov     ecx, 40h ; '@'; uFlags
0x18000f5dc  mov     r13d, eax
0x18000f5df  mov     edi, 8007000Eh
0x18000f5e4  call    cs:__imp_LocalAlloc
0x18000f5ea  mov     rbp, rax
0x18000f5ed  test    rax, rax
0x18000f5f0  jz      short loc_18000F667
0x18000f5f2  mov     r8, rsi; pSourceSid
0x18000f5f5  mov     rdx, rax; pDestinationSid
0x18000f5f8  mov     ecx, r13d; nDestinationSidLength
0x18000f5fb  call    cs:__imp_CopySid
0x18000f601  test    eax, eax
0x18000f603  jz      loc_18000F6AD
0x18000f609  xor     edi, edi
0x18000f60b  movzx   eax, byte ptr [rsp+78h+arg_8]
0x18000f613  lea     rdx, GenericMapping; GenericMapping
0x18000f61a  mov     [rbx+8], rbp
0x18000f61e  lea     rcx, [rbx+4]; AccessMask
0x18000f622  mov     [rbx+1], al
0x18000f625  movzx   eax, [rsp+78h+arg_10]
0x18000f62d  mov     [rbx+2], ax
0x18000f631  mov     eax, [rsp+78h+arg_18]
0x18000f638  mov     [rbx+4], eax
0x18000f63b  mov     [rbx], r12b
0x18000f63e  call    cs:__imp_RtlMapGenericMask
0x18000f644  movzx   ecx, byte ptr [rbx]
0x18000f647  mov     eax, 80000000h
0x18000f64c  mov     [rbx+1Ch], eax
0x18000f64f  test    cl, cl
0x18000f651  jnz     short loc_18000F679
0x18000f653  mov     eax, 80000001h
0x18000f658  mov     [rbx+1Ch], eax
0x18000f65b  test    byte ptr [rbx+1], 10h
0x18000f65f  jz      short loc_18000F667
0x18000f661  or      eax, 20h
0x18000f664  mov     [rbx+1Ch], eax
0x18000f667  mov     r13, [rsp+78h+var_30]
0x18000f66c  mov     rbp, [rsp+78h+arg_0]
0x18000f674  jmp     loc_18000F59E
0x18000f679  cmp     cl, 9
0x18000f67c  jnz     short loc_18000F65B
0x18000f67e  jmp     short loc_18000F653
0x18000f680  mov     edi, 80070057h
0x18000f685  mov     rcx, rbx; this
0x18000f688  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000f68d  mov     r14, [rsp+78h+var_38]
0x18000f692  mov     eax, edi
0x18000f694  add     rsp, 58h
0x18000f698  pop     r15
0x18000f69a  pop     rdi
0x18000f69b  pop     rsi
0x18000f69c  pop     rbx
0x18000f69d  retn
0x18000f69e  mov     eax, 8007000Eh
0x18000f6a3  add     rsp, 58h
0x18000f6a7  pop     r15
0x18000f6a9  pop     rdi
0x18000f6aa  pop     rsi
0x18000f6ab  pop     rbx
0x18000f6ac  retn
0x18000f6ad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000f6b2  mov     edi, eax
0x18000f6b4  test    eax, eax
0x18000f6b6  jns     loc_18000F60B
0x18000f6bc  mov     rcx, rbp; hMem
0x18000f6bf  call    cs:__imp_LocalFree
0x18000f6c5  jmp     short loc_18000F667
0x18000f6c7  mov     rcx, rsi; pSid
0x18000f6ca  call    cs:__imp_GetLengthSid
0x18000f6d0  movzx   r9d, byte ptr [rdi+1]; unsigned __int8
0x18000f6d5  mov     rdx, rsi; void *
0x18000f6d8  mov     r8d, [rdi+4]; unsigned int
0x18000f6dc  mov     ecx, eax
0x18000f6de  movzx   eax, word ptr [rdi+2]
0x18000f6e2  add     rcx, rsi
0x18000f6e5  mov     [rsp+78h+var_48], rcx; void *
0x18000f6ea  mov     rcx, rbx; this
0x18000f6ed  mov     [rsp+78h+var_50], ax; unsigned __int16
0x18000f6f2  movzx   eax, byte ptr [rdi]
0x18000f6f5  mov     [rsp+78h+var_58], al; unsigned __int8
0x18000f6f9  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x18000f6fe  mov     edi, eax
0x18000f700  jmp     loc_18000F59E
0x18000f705  mov     edi, 80070057h
0x18000f70a  jmp     loc_18000F59E
```
