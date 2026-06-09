# MountMgrNextDriveLetterWorker

- ea: `0x140019af0`
- end: `0x140019c91`
- name: `MountMgrNextDriveLetterWorker`
- size: `417`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c730`
- `0x14001aab0`

## callees

- `0x140002d70`
- `0x14000a640`
- `0x14000be4c`
- `0x140019af0`
- `0x140019ca0`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019ba3`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019bc5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019ba3`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140019bc5`

## pseudocode

```c
__int64 __fastcall MountMgrNextDriveLetterWorker(_QWORD *Context, __int64 a2, _BYTE *a3)
{
  __int64 *v3; // rbx
  __int64 v4; // rsi
  __int64 result; // rax
  unsigned __int8 v9; // bl
  __int64 v10; // xmm1_8
  __int16 v11; // ax
  UNICODE_STRING v12; // [rsp+20h] [rbp-88h] BYREF
  __int128 v13; // [rsp+30h] [rbp-78h] BYREF
  __int64 v14; // [rsp+40h] [rbp-68h]
  __int16 v15; // [rsp+48h] [rbp-60h]
  __int16 v16; // [rsp+4Ah] [rbp-5Eh]

  v3 = *(__int64 **)(a2 + 16);
  v4 = a2 + 16;
  v12 = 0;
  while ( v3 != (__int64 *)v4 )
  {
    if ( (unsigned __int8)IsDriveLetter((PCUNICODE_STRING)(v3 + 3)) && *((_BYTE *)v3 + 16) )
    {
      *a3 = 0;
      result = 0;
      a3[1] = *(_BYTE *)(v3[4] + 24);
      return result;
    }
    v3 = (__int64 *)*v3;
  }
  if ( (*(_DWORD *)(a2 + 120) & 0x100) == 0
    && (*(_BYTE *)(a2 + 127)
     || (unsigned __int8)HasNoDriveLetterEntry(*(_QWORD *)(a2 + 96))
     || !*((_BYTE *)Context + 192) && !*(_BYTE *)(a2 + 124)) )
  {
    result = 0;
LABEL_22:
    *(_WORD *)a3 = 0;
    return result;
  }
  *a3 = 1;
  if ( RtlPrefixUnicodeString(&String1, (PCUNICODE_STRING)(a2 + 80), 1u) )
    v9 = 65;
  else
    v9 = (RtlPrefixUnicodeString(&stru_140007030, (PCUNICODE_STRING)(a2 + 80), 1u) != 0) + 67;
  *(_DWORD *)&v12.Length = 1835036;
  v12.Buffer = (PWSTR)&v13;
  v13 = *(_OWORD *)String2.Buffer;
  v10 = *((_QWORD *)String2.Buffer + 2);
  v16 = 58;
  v11 = *(unsigned __int8 *)(a2 + 128);
  v14 = v10;
  if ( !(_BYTE)v11 || (a3[1] = v11, v15 = v11, result = MountMgrCreatePointWorker(Context, &v12, a2), (int)result < 0) )
  {
    while ( 1 )
    {
      a3[1] = v9;
      if ( v9 > 0x5Au )
        break;
      v12.Buffer[12] = v9;
      result = MountMgrCreatePointWorker(Context, &v12, a2);
      if ( (int)result >= 0 )
        return result;
      v9 = a3[1] + 1;
    }
    result = 0;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x140019af0  mov     [rsp+arg_18], rbx
0x140019af5  push    rbp
0x140019af6  push    rsi
0x140019af7  push    rdi
0x140019af8  push    r14
0x140019afa  push    r15
0x140019afc  sub     rsp, 80h
0x140019b03  mov     rax, cs:__security_cookie
0x140019b0a  xor     rax, rsp
0x140019b0d  mov     [rsp+0A8h+var_38], rax
0x140019b12  mov     rbx, [rdx+10h]
0x140019b16  lea     rsi, [rdx+10h]
0x140019b1a  xorps   xmm0, xmm0
0x140019b1d  mov     rdi, r8
0x140019b20  movups  [rsp+0A8h+var_88], xmm0
0x140019b25  mov     r14, rdx
0x140019b28  mov     r15, rcx
0x140019b2b  xor     ebp, ebp
0x140019b2d  cmp     rbx, rsi
0x140019b30  jz      short loc_140019B5F
0x140019b32  lea     rcx, [rbx+18h]; String2
0x140019b36  call    IsDriveLetter
0x140019b3b  test    al, al
0x140019b3d  jz      short loc_140019B45
0x140019b3f  cmp     [rbx+10h], bpl
0x140019b43  jnz     short loc_140019B4A
0x140019b45  mov     rbx, [rbx]
0x140019b48  jmp     short loc_140019B2D
0x140019b4a  mov     [rdi], bpl
0x140019b4d  mov     eax, ebp
0x140019b4f  mov     rcx, [rbx+20h]
0x140019b53  movzx   edx, byte ptr [rcx+18h]
0x140019b57  mov     [rdi+1], dl
0x140019b5a  jmp     loc_140019C6C
0x140019b5f  test    dword ptr [r14+78h], 100h
0x140019b67  jnz     short loc_140019B92
0x140019b69  cmp     [r14+7Fh], bpl
0x140019b6d  jnz     short loc_140019B8B
0x140019b6f  mov     rcx, [r14+60h]
0x140019b73  call    HasNoDriveLetterEntry
0x140019b78  test    al, al
0x140019b7a  jnz     short loc_140019B8B
0x140019b7c  cmp     [r15+0C0h], bpl
0x140019b83  jnz     short loc_140019B92
0x140019b85  cmp     [r14+7Ch], bpl
0x140019b89  jnz     short loc_140019B92
0x140019b8b  mov     eax, ebp
0x140019b8d  jmp     loc_140019C69
0x140019b92  mov     r8b, 1; CaseInSensitive
0x140019b95  mov     byte ptr [rdi], 1
0x140019b98  lea     rdx, [r14+50h]; String2
0x140019b9c  lea     rcx, String1; String1
0x140019ba3  call    cs:__imp_RtlPrefixUnicodeString
0x140019baa  nop     dword ptr [rax+rax+00h]
0x140019baf  test    al, al
0x140019bb1  jz      short loc_140019BB7
0x140019bb3  mov     bl, 41h ; 'A'
0x140019bb5  jmp     short loc_140019BD9
0x140019bb7  mov     r8b, 1; CaseInSensitive
0x140019bba  lea     rdx, [r14+50h]; String2
0x140019bbe  lea     rcx, stru_140007030; String1
0x140019bc5  call    cs:__imp_RtlPrefixUnicodeString
0x140019bcc  nop     dword ptr [rax+rax+00h]
0x140019bd1  test    al, al
0x140019bd3  setnz   bl
0x140019bd6  add     bl, 43h ; 'C'
0x140019bd9  lea     rax, [rsp+0A8h+var_78]
0x140019bde  mov     dword ptr [rsp+0A8h+var_88], 1C001Ch
0x140019be6  mov     qword ptr [rsp+0A8h+var_88+8], rax
0x140019beb  mov     rax, cs:String2.Buffer
0x140019bf2  movups  xmm0, xmmword ptr [rax]
0x140019bf5  movups  [rsp+0A8h+var_78], xmm0
0x140019bfa  movsd   xmm1, qword ptr [rax+10h]
0x140019bff  mov     eax, 3Ah ; ':'
0x140019c04  mov     [rsp+0A8h+var_5E], ax
0x140019c09  movzx   eax, byte ptr [r14+80h]
0x140019c11  movsd   [rsp+0A8h+var_68], xmm1
0x140019c17  test    al, al
0x140019c19  jz      short loc_140019C37
0x140019c1b  mov     r8, r14
0x140019c1e  mov     [rdi+1], al
0x140019c21  lea     rdx, [rsp+0A8h+var_88]
0x140019c26  mov     [rsp+0A8h+var_60], ax
0x140019c2b  mov     rcx, r15; Context
0x140019c2e  call    MountMgrCreatePointWorker
0x140019c33  test    eax, eax
0x140019c35  jns     short loc_140019C6C
0x140019c37  mov     [rdi+1], bl
0x140019c3a  cmp     bl, 5Ah ; 'Z'
0x140019c3d  ja      short loc_140019C67
0x140019c3f  mov     rax, qword ptr [rsp+0A8h+var_88+8]
0x140019c44  lea     rdx, [rsp+0A8h+var_88]
0x140019c49  movzx   ecx, bl
0x140019c4c  mov     r8, r14
0x140019c4f  mov     [rax+18h], cx
0x140019c53  mov     rcx, r15; Context
0x140019c56  call    MountMgrCreatePointWorker
0x140019c5b  test    eax, eax
0x140019c5d  jns     short loc_140019C6C
0x140019c5f  movzx   ebx, byte ptr [rdi+1]
0x140019c63  inc     bl
0x140019c65  jmp     short loc_140019C37
0x140019c67  xor     eax, eax
0x140019c69  mov     [rdi], bp
0x140019c6c  mov     rcx, [rsp+0A8h+var_38]
0x140019c71  xor     rcx, rsp; StackCookie
0x140019c74  call    __security_check_cookie
0x140019c79  mov     rbx, [rsp+0A8h+arg_18]
0x140019c81  add     rsp, 80h
0x140019c88  pop     r15
0x140019c8a  pop     r14
0x140019c8c  pop     rdi
0x140019c8d  pop     rsi
0x140019c8e  pop     rbp
0x140019c8f  retn
```
