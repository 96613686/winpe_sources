# STRA::CopyBinary(void *,ulong)

- ea: `0x18001ce20`
- end: `0x18001cffd`
- name: `?CopyBinary@STRA@@QEAAJPEAXK@Z`
- size: `477`
- prototype: `__int64 __fastcall(STRA *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000c350`
- `0x18000cd40`
- `0x180010910`
- `0x18001ce20`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!strcat_s` at `0x18001cf07`
- `msvcrt!strcat_s` at `0x18001cf2d`
- `msvcrt!strcat_s` at `0x18001cf50`
- `msvcrt!strcat_s` at `0x18001cf07`
- `msvcrt!strcat_s` at `0x18001cf2d`
- `msvcrt!strcat_s` at `0x18001cf50`
- `msvcrt!sprintf_s` at `0x18001cef3`
- `msvcrt!sprintf_s` at `0x18001cf8e`
- `msvcrt!sprintf_s` at `0x18001cef3`
- `msvcrt!sprintf_s` at `0x18001cf8e`

## pseudocode

```c
int __fastcall STRA::CopyBinary(STRA *this, unsigned __int8 *a2, unsigned int a3)
{
  int result; // eax
  unsigned int i; // esi
  __int64 v8; // rdi
  int v9; // ebx
  char v10; // dl
  __int64 v11; // r8
  char Buffer[8]; // [rsp+30h] [rbp-99h] BYREF
  __int128 v13; // [rsp+38h] [rbp-91h] BYREF
  char v14; // [rsp+48h] [rbp-81h]
  char Destination[16]; // [rsp+50h] [rbp-79h] BYREF
  __int128 v16; // [rsp+60h] [rbp-69h]
  __int128 v17; // [rsp+70h] [rbp-59h]
  int v18; // [rsp+80h] [rbp-49h]
  char v19[80]; // [rsp+90h] [rbp-39h] BYREF

  *(_DWORD *)Buffer = 0;
  v18 = 0;
  v14 = 0;
  *(_OWORD *)Destination = 0;
  v16 = 0;
  v17 = 0;
  v13 = 0;
  memset_0(v19, 0, 0x4Eu);
  if ( !a3 || !a2 )
    return STRA::Copy(this, "00000000                         -\r\n");
  result = STRA::Resize(this, 77 * (a3 >> 4) + 1);
  if ( result >= 0 )
  {
    for ( i = 0; i < a3; i += 16 )
    {
      Destination[0] = 0;
      v8 = 0;
      LOBYTE(v13) = 0;
      do
      {
        while ( 1 )
        {
          if ( (unsigned int)v8 + i >= a3 )
          {
            strcat_s(Destination, 0x34u, "   ");
            v10 = 32;
          }
          else
          {
            v9 = a2[(unsigned int)v8 + (unsigned __int64)i];
            sprintf_s(Buffer, 4u, "%02x ", v9);
            strcat_s(Destination, 0x34u, Buffer);
            v10 = 46;
            if ( (unsigned __int8)(v9 - 32) <= 0x8Fu )
              v10 = v9;
          }
          *((_BYTE *)&v13 + v8) = v10;
          if ( (_DWORD)v8 != 7 )
            break;
          strcat_s(Destination, 0x34u, "- ");
          v8 = 8;
        }
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < 0x10 );
      sprintf_s(v19, 0x4Eu, "%08x %s%s\r\n", i, Destination, (const char *)&v13);
      v11 = -1;
      do
        ++v11;
      while ( v19[v11] );
      result = STRA::AuxAppend(this, (const unsigned __int8 *)v19, v11, *((_DWORD *)this + 12), 1);
      if ( result < 0 )
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ce20  mov     [rsp-8+arg_18], rbx
0x18001ce25  push    rbp
0x18001ce26  push    rsi
0x18001ce27  push    rdi
0x18001ce28  push    r12
0x18001ce2a  push    r13
0x18001ce2c  push    r14
0x18001ce2e  push    r15
0x18001ce30  lea     rbp, [rsp-27h]
0x18001ce35  sub     rsp, 0F0h
0x18001ce3c  mov     rax, cs:__security_cookie
0x18001ce43  xor     rax, rsp
0x18001ce46  mov     [rbp+57h+var_40], rax
0x18001ce4a  xorps   xmm0, xmm0
0x18001ce4d  mov     dword ptr [rsp+120h+Buffer], 0
0x18001ce55  xor     eax, eax
0x18001ce57  mov     r15d, r8d
0x18001ce5a  mov     r12, rdx
0x18001ce5d  mov     [rbp+57h+var_A0], eax
0x18001ce60  mov     r13, rcx
0x18001ce63  mov     [rsp+120h+var_D8], al
0x18001ce67  xor     edx, edx; Val
0x18001ce69  lea     rcx, [rbp+57h+var_90]; void *
0x18001ce6d  lea     r8d, [rax+4Eh]; Size
0x18001ce71  movups  xmmword ptr [rbp+57h+Destination], xmm0
0x18001ce75  movups  [rbp+57h+var_C0], xmm0
0x18001ce79  movups  [rbp+57h+var_B0], xmm0
0x18001ce7d  movups  [rsp+120h+var_E8], xmm0
0x18001ce82  call    memset_0
0x18001ce87  test    r15d, r15d
0x18001ce8a  jz      loc_18001CFC7
0x18001ce90  test    r12, r12
0x18001ce93  jz      loc_18001CFC7
0x18001ce99  mov     eax, r15d
0x18001ce9c  mov     rcx, r13; this
0x18001ce9f  shr     eax, 4
0x18001cea2  imul    edx, eax, 4Dh ; 'M'
0x18001cea5  inc     edx; unsigned int
0x18001cea7  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001ceac  test    eax, eax
0x18001ceae  js      loc_18001CFD6
0x18001ceb4  xor     esi, esi
0x18001ceb6  cmp     esi, r15d
0x18001ceb9  jnb     loc_18001CFD6
0x18001cebf  mov     [rbp+57h+Destination], 0
0x18001cec3  xor     edi, edi
0x18001cec5  mov     byte ptr [rsp+120h+var_E8], 0
0x18001ceca  lea     eax, [rdi+rsi]
0x18001cecd  mov     r14d, edi
0x18001ced0  cmp     eax, r15d
0x18001ced3  jnb     short loc_18001CF1D
0x18001ced5  mov     eax, esi
0x18001ced7  lea     r8, a02x; "%02x "
0x18001cede  add     rax, r14
0x18001cee1  lea     rcx, [rsp+120h+Buffer]; Buffer
0x18001cee6  mov     edx, 4; BufferCount
0x18001ceeb  movzx   ebx, byte ptr [rax+r12]
0x18001cef0  mov     r9d, ebx
0x18001cef3  call    cs:__imp_sprintf_s
0x18001cef9  lea     r8, [rsp+120h+Buffer]; Source
0x18001cefe  mov     edx, 34h ; '4'; SizeInBytes
0x18001cf03  lea     rcx, [rbp+57h+Destination]; Destination
0x18001cf07  call    cs:__imp_strcat_s
0x18001cf0d  lea     ecx, [rbx-20h]
0x18001cf10  mov     edx, 2Eh ; '.'
0x18001cf15  cmp     cl, 8Fh
0x18001cf18  cmovbe  edx, ebx
0x18001cf1b  jmp     short loc_18001CF35
0x18001cf1d  lea     r8, asc_180031DD0; "   "
0x18001cf24  mov     edx, 34h ; '4'; SizeInBytes
0x18001cf29  lea     rcx, [rbp+57h+Destination]; Destination
0x18001cf2d  call    cs:__imp_strcat_s
0x18001cf33  mov     dl, 20h ; ' '
0x18001cf35  lea     rax, [rsp+120h+var_E8]
0x18001cf3a  mov     [rdi+rax], dl
0x18001cf3d  cmp     edi, 7
0x18001cf40  jnz     short loc_18001CF5D
0x18001cf42  lea     r8, asc_180031DD4; "- "
0x18001cf49  lea     edx, [rdi+2Dh]; SizeInBytes
0x18001cf4c  lea     rcx, [rbp+57h+Destination]; Destination
0x18001cf50  call    cs:__imp_strcat_s
0x18001cf56  inc     edi
0x18001cf58  jmp     loc_18001CECA
0x18001cf5d  inc     edi
0x18001cf5f  cmp     edi, 10h
0x18001cf62  jb      loc_18001CECA
0x18001cf68  lea     rax, [rsp+120h+var_E8]
0x18001cf6d  mov     r9d, esi
0x18001cf70  mov     [rsp+120h+var_F8], rax
0x18001cf75  lea     r8, a08xSS; "%08x %s%s\r\n"
0x18001cf7c  lea     rax, [rbp+57h+Destination]
0x18001cf80  mov     edx, 4Eh ; 'N'; BufferCount
0x18001cf85  lea     rcx, [rbp+57h+var_90]; Buffer
0x18001cf89  mov     qword ptr [rsp+120h+var_100], rax
0x18001cf8e  call    cs:__imp_sprintf_s
0x18001cf94  lea     rax, [rbp+57h+var_90]
0x18001cf98  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cf9c  inc     r8; unsigned int
0x18001cf9f  cmp     byte ptr [rax+r8], 0
0x18001cfa4  jnz     short loc_18001CF9C
0x18001cfa6  mov     r9d, [r13+30h]; unsigned int
0x18001cfaa  lea     rdx, [rbp+57h+var_90]; unsigned __int8 *
0x18001cfae  mov     rcx, r13; this
0x18001cfb1  mov     [rsp+120h+var_100], 1; bool
0x18001cfb6  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x18001cfbb  test    eax, eax
0x18001cfbd  js      short loc_18001CFD6
0x18001cfbf  add     esi, 10h
0x18001cfc2  jmp     loc_18001CEB6
0x18001cfc7  lea     rdx, Src; "00000000                         -\r\n"
0x18001cfce  mov     rcx, r13; this
0x18001cfd1  call    ?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18001cfd6  mov     rcx, [rbp+57h+var_40]
0x18001cfda  xor     rcx, rsp; StackCookie
0x18001cfdd  call    __security_check_cookie
0x18001cfe2  mov     rbx, [rsp+120h+arg_18]
0x18001cfea  add     rsp, 0F0h
0x18001cff1  pop     r15
0x18001cff3  pop     r14
0x18001cff5  pop     r13
0x18001cff7  pop     r12
0x18001cff9  pop     rdi
0x18001cffa  pop     rsi
0x18001cffb  pop     rbp
0x18001cffc  retn
```
