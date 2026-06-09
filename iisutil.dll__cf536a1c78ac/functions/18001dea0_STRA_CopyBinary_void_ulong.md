# STRA::CopyBinary(void *,ulong)

- ea: `0x18001dea0`
- end: `0x18001e09c`
- name: `?CopyBinary@STRA@@QEAAJPEAXK@Z`
- size: `508`
- prototype: `int __fastcall(STRA *this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000d2e0`
- `0x18000ddb0`
- `0x180011b40`
- `0x18001dea0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!strcat_s` at `0x18001df8d`
- `msvcrt!strcat_s` at `0x18001dfb9`
- `msvcrt!strcat_s` at `0x18001dfe2`
- `msvcrt!strcat_s` at `0x18001df8d`
- `msvcrt!strcat_s` at `0x18001dfb9`
- `msvcrt!strcat_s` at `0x18001dfe2`
- `msvcrt!sprintf_s` at `0x18001df73`
- `msvcrt!sprintf_s` at `0x18001e026`
- `msvcrt!sprintf_s` at `0x18001df73`
- `msvcrt!sprintf_s` at `0x18001e026`

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
0x18001dea0  mov     [rsp-8+arg_18], rbx
0x18001dea5  push    rbp
0x18001dea6  push    rsi
0x18001dea7  push    rdi
0x18001dea8  push    r12
0x18001deaa  push    r13
0x18001deac  push    r14
0x18001deae  push    r15
0x18001deb0  lea     rbp, [rsp-27h]
0x18001deb5  sub     rsp, 0F0h
0x18001debc  mov     rax, cs:__security_cookie
0x18001dec3  xor     rax, rsp
0x18001dec6  mov     [rbp+57h+var_40], rax
0x18001deca  xorps   xmm0, xmm0
0x18001decd  mov     dword ptr [rsp+120h+Buffer], 0
0x18001ded5  xor     eax, eax
0x18001ded7  mov     r15d, r8d
0x18001deda  mov     r12, rdx
0x18001dedd  mov     [rbp+57h+var_A0], eax
0x18001dee0  mov     r13, rcx
0x18001dee3  mov     [rsp+120h+var_D8], al
0x18001dee7  xor     edx, edx; Val
0x18001dee9  lea     rcx, [rbp+57h+var_90]; void *
0x18001deed  lea     r8d, [rax+4Eh]; Size
0x18001def1  movups  xmmword ptr [rbp+57h+Destination], xmm0
0x18001def5  movups  [rbp+57h+var_C0], xmm0
0x18001def9  movups  [rbp+57h+var_B0], xmm0
0x18001defd  movups  [rsp+120h+var_E8], xmm0
0x18001df02  call    memset_0
0x18001df07  test    r15d, r15d
0x18001df0a  jz      loc_18001E065
0x18001df10  test    r12, r12
0x18001df13  jz      loc_18001E065
0x18001df19  mov     eax, r15d
0x18001df1c  mov     rcx, r13; this
0x18001df1f  shr     eax, 4
0x18001df22  imul    edx, eax, 4Dh ; 'M'
0x18001df25  inc     edx; unsigned int
0x18001df27  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001df2c  test    eax, eax
0x18001df2e  js      loc_18001E074
0x18001df34  xor     esi, esi
0x18001df36  cmp     esi, r15d
0x18001df39  jnb     loc_18001E074
0x18001df3f  mov     [rbp+57h+Destination], 0
0x18001df43  xor     edi, edi
0x18001df45  mov     byte ptr [rsp+120h+var_E8], 0
0x18001df4a  lea     eax, [rdi+rsi]
0x18001df4d  mov     r14d, edi
0x18001df50  cmp     eax, r15d
0x18001df53  jnb     short loc_18001DFA9
0x18001df55  mov     eax, esi
0x18001df57  lea     r8, a02x; "%02x "
0x18001df5e  add     rax, r14
0x18001df61  lea     rcx, [rsp+120h+Buffer]; Buffer
0x18001df66  mov     edx, 4; BufferCount
0x18001df6b  movzx   ebx, byte ptr [rax+r12]
0x18001df70  mov     r9d, ebx
0x18001df73  call    cs:__imp_sprintf_s
0x18001df7a  nop     dword ptr [rax+rax+00h]
0x18001df7f  lea     r8, [rsp+120h+Buffer]; Source
0x18001df84  mov     edx, 34h ; '4'; SizeInBytes
0x18001df89  lea     rcx, [rbp+57h+Destination]; Destination
0x18001df8d  call    cs:__imp_strcat_s
0x18001df94  nop     dword ptr [rax+rax+00h]
0x18001df99  lea     ecx, [rbx-20h]
0x18001df9c  mov     edx, 2Eh ; '.'
0x18001dfa1  cmp     cl, 8Fh
0x18001dfa4  cmovbe  edx, ebx
0x18001dfa7  jmp     short loc_18001DFC7
0x18001dfa9  lea     r8, asc_180033DD0; "   "
0x18001dfb0  mov     edx, 34h ; '4'; SizeInBytes
0x18001dfb5  lea     rcx, [rbp+57h+Destination]; Destination
0x18001dfb9  call    cs:__imp_strcat_s
0x18001dfc0  nop     dword ptr [rax+rax+00h]
0x18001dfc5  mov     dl, 20h ; ' '
0x18001dfc7  lea     rax, [rsp+120h+var_E8]
0x18001dfcc  mov     [rdi+rax], dl
0x18001dfcf  cmp     edi, 7
0x18001dfd2  jnz     short loc_18001DFF5
0x18001dfd4  lea     r8, asc_180033DD4; "- "
0x18001dfdb  lea     edx, [rdi+2Dh]; SizeInBytes
0x18001dfde  lea     rcx, [rbp+57h+Destination]; Destination
0x18001dfe2  call    cs:__imp_strcat_s
0x18001dfe9  nop     dword ptr [rax+rax+00h]
0x18001dfee  inc     edi
0x18001dff0  jmp     loc_18001DF4A
0x18001dff5  inc     edi
0x18001dff7  cmp     edi, 10h
0x18001dffa  jb      loc_18001DF4A
0x18001e000  lea     rax, [rsp+120h+var_E8]
0x18001e005  mov     r9d, esi
0x18001e008  mov     [rsp+120h+var_F8], rax
0x18001e00d  lea     r8, a08xSS; "%08x %s%s\r\n"
0x18001e014  lea     rax, [rbp+57h+Destination]
0x18001e018  mov     edx, 4Eh ; 'N'; BufferCount
0x18001e01d  lea     rcx, [rbp+57h+var_90]; Buffer
0x18001e021  mov     qword ptr [rsp+120h+var_100], rax
0x18001e026  call    cs:__imp_sprintf_s
0x18001e02d  nop     dword ptr [rax+rax+00h]
0x18001e032  lea     rax, [rbp+57h+var_90]
0x18001e036  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e03a  inc     r8; unsigned int
0x18001e03d  cmp     byte ptr [rax+r8], 0
0x18001e042  jnz     short loc_18001E03A
0x18001e044  mov     r9d, [r13+30h]; unsigned int
0x18001e048  lea     rdx, [rbp+57h+var_90]; unsigned __int8 *
0x18001e04c  mov     rcx, r13; this
0x18001e04f  mov     [rsp+120h+var_100], 1; bool
0x18001e054  call    ?AuxAppend@STRA@@AEAAJPEBEKK_N@Z; STRA::AuxAppend(uchar const *,ulong,ulong,bool)
0x18001e059  test    eax, eax
0x18001e05b  js      short loc_18001E074
0x18001e05d  add     esi, 10h
0x18001e060  jmp     loc_18001DF36
0x18001e065  lea     rdx, Src; "00000000                         -\r\n"
0x18001e06c  mov     rcx, r13; this
0x18001e06f  call    ?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18001e074  mov     rcx, [rbp+57h+var_40]
0x18001e078  xor     rcx, rsp; StackCookie
0x18001e07b  call    __security_check_cookie
0x18001e080  mov     rbx, [rsp+120h+arg_18]
0x18001e088  add     rsp, 0F0h
0x18001e08f  pop     r15
0x18001e091  pop     r14
0x18001e093  pop     r13
0x18001e095  pop     r12
0x18001e097  pop     rdi
0x18001e098  pop     rsi
0x18001e099  pop     rbp
0x18001e09a  retn
```
