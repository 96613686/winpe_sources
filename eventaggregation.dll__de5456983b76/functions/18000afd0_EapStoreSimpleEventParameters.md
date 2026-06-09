# EapStoreSimpleEventParameters

- ea: `0x18000afd0`
- end: `0x18000b110`
- name: `EapStoreSimpleEventParameters`
- size: `320`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, GUID *Guid)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ad20`
- `0x18000aec4`

## callees

- `0x18000ab18`
- `0x18000afd0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000b0fb`
- `ntdll!RtlFreeUnicodeString` at `0x18000b0fb`
- `ntdll!RtlStringFromGUID` at `0x18000aff3`
- `ntdll!RtlStringFromGUID` at `0x18000aff3`

## pseudocode

```c
__int64 __fastcall EapStoreSimpleEventParameters(HANDLE KeyHandle, GUID *Guid)
{
  NTSTATUS v4; // ebx
  unsigned __int16 i; // di
  __int64 v6; // r10
  __int64 v7; // rdx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  ULONG v12; // eax
  __int64 v13; // rax
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-48h] BYREF

  GuidString = 0;
  v4 = RtlStringFromGUID(Guid, &GuidString);
  if ( v4 >= 0 )
  {
    v4 = EapSetValue(KeyHandle, GuidString.Length);
    if ( v4 >= 0 )
    {
      for ( i = 0; i < LOWORD(Guid[1].Data1); ++i )
      {
        v6 = *(_QWORD *)Guid[1].Data4;
        v7 = 32LL * i;
        v8 = *(_DWORD *)(v7 + v6 + 8);
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                if ( v11 != 1 )
                {
                  v4 = -1073741595;
                  break;
                }
                v12 = *(unsigned __int16 *)(v7 + v6 + 16);
              }
              else
              {
                v12 = 2 * *(unsigned __int16 *)(v7 + v6 + 16);
              }
            }
            else
            {
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)(*(_QWORD *)(v7 + v6 + 16) + 2 * v13) );
              v12 = 2 * v13 + 2;
            }
          }
          else
          {
            v12 = 8;
          }
        }
        else
        {
          v12 = 4;
        }
        v4 = EapSetValue(KeyHandle, v12);
        if ( v4 < 0 )
          break;
      }
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000afd0  push    rbx
0x18000afd2  push    rbp
0x18000afd3  push    rsi
0x18000afd4  push    rdi
0x18000afd5  push    r14
0x18000afd7  push    r15
0x18000afd9  sub     rsp, 48h
0x18000afdd  mov     rsi, rdx
0x18000afe0  mov     rbp, rcx
0x18000afe3  xorps   xmm0, xmm0
0x18000afe6  lea     rdx, [rsp+78h+GuidString]; GuidString
0x18000afeb  mov     rcx, rsi; Guid
0x18000afee  movups  xmmword ptr [rsp+78h+GuidString.Length], xmm0
0x18000aff3  call    cs:__imp_RtlStringFromGUID
0x18000aff9  xor     r14d, r14d
0x18000affc  mov     ebx, eax
0x18000affe  test    eax, eax
0x18000b000  js      loc_18000B0EF
0x18000b006  movzx   eax, [rsp+78h+GuidString.Length]
0x18000b00b  lea     r15d, [r14+1]
0x18000b00f  mov     r9, [rsp+78h+GuidString.Buffer]
0x18000b014  mov     r8d, r15d
0x18000b017  xor     edx, edx
0x18000b019  mov     [rsp+78h+var_58], eax; ULONG
0x18000b01d  mov     rcx, rbp; KeyHandle
0x18000b020  call    EapSetValue
0x18000b025  mov     ebx, eax
0x18000b027  test    eax, eax
0x18000b029  js      loc_18000B0EF
0x18000b02f  mov     edi, r14d
0x18000b032  cmp     di, [rsi+10h]
0x18000b036  jnb     loc_18000B0EF
0x18000b03c  mov     r10, [rsi+18h]
0x18000b040  movzx   edx, di
0x18000b043  shl     rdx, 5
0x18000b047  mov     ecx, [rdx+r10+8]
0x18000b04c  test    ecx, ecx
0x18000b04e  jz      short loc_18000B0BB
0x18000b050  sub     ecx, r15d
0x18000b053  jz      short loc_18000B0AF
0x18000b055  sub     ecx, r15d
0x18000b058  jz      short loc_18000B090
0x18000b05a  sub     ecx, r15d
0x18000b05d  jz      short loc_18000B07B
0x18000b05f  cmp     ecx, r15d
0x18000b062  jnz     loc_18000B0EA
0x18000b068  mov     r9, [rdx+r10+18h]
0x18000b06d  mov     r8d, 3
0x18000b073  movzx   eax, word ptr [rdx+r10+10h]
0x18000b079  jmp     short loc_18000B0CB
0x18000b07b  movzx   eax, word ptr [rdx+r10+10h]
0x18000b081  mov     r8d, 7
0x18000b087  mov     r9, [rdx+r10+18h]
0x18000b08c  add     eax, eax
0x18000b08e  jmp     short loc_18000B0CB
0x18000b090  mov     r9, [rdx+r10+10h]
0x18000b095  mov     r8d, r15d
0x18000b098  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b09c  inc     rax
0x18000b09f  cmp     [r9+rax*2], r14w
0x18000b0a4  jnz     short loc_18000B09C
0x18000b0a6  lea     eax, ds:2[rax*2]
0x18000b0ad  jmp     short loc_18000B0CB
0x18000b0af  mov     r8d, 0Bh
0x18000b0b5  lea     eax, [r8-3]
0x18000b0b9  jmp     short loc_18000B0C4
0x18000b0bb  mov     r8d, 4
0x18000b0c1  mov     eax, r8d
0x18000b0c4  lea     r9, [r10+10h]
0x18000b0c8  add     r9, rdx
0x18000b0cb  mov     rdx, [rdx+r10]
0x18000b0cf  mov     rcx, rbp; KeyHandle
0x18000b0d2  mov     [rsp+78h+var_58], eax; ULONG
0x18000b0d6  call    EapSetValue
0x18000b0db  mov     ebx, eax
0x18000b0dd  test    eax, eax
0x18000b0df  js      short loc_18000B0EF
0x18000b0e1  add     di, r15w
0x18000b0e5  jmp     loc_18000B032
0x18000b0ea  mov     ebx, 0C00000E5h
0x18000b0ef  cmp     [rsp+78h+GuidString.Buffer], r14
0x18000b0f4  jz      short loc_18000B101
0x18000b0f6  lea     rcx, [rsp+78h+GuidString]; UnicodeString
0x18000b0fb  call    cs:__imp_RtlFreeUnicodeString
0x18000b101  mov     eax, ebx
0x18000b103  add     rsp, 48h
0x18000b107  pop     r15
0x18000b109  pop     r14
0x18000b10b  pop     rdi
0x18000b10c  pop     rsi
0x18000b10d  pop     rbp
0x18000b10e  pop     rbx
0x18000b10f  retn
```
