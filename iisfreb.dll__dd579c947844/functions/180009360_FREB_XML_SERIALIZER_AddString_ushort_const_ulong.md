# FREB_XML_SERIALIZER::AddString(ushort const *,ulong)

- ea: `0x180009360`
- end: `0x180009450`
- name: `?AddString@FREB_XML_SERIALIZER@@QEAAXPEBGK@Z`
- size: `240`
- prototype: `void __fastcall(FREB_XML_SERIALIZER *this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004ae4`
- `0x1800095dc`
- `0x180009948`

## callees

- `0x180009360`
- `0x180009690`
- `0x18000ac46`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093df`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800093d5`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x1800093d5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000939a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000939a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009427`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180009427`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddString(FREB_XML_SERIALIZER *this, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // r8
  signed int LastError; // eax
  unsigned __int8 *Memory; // rax
  _BYTE v9[32]; // [rsp+20h] [rbp-E8h] BYREF
  void *Src; // [rsp+40h] [rbp-C8h]
  size_t Size; // [rsp+50h] [rbp-B8h]
  char v12[128]; // [rsp+60h] [rbp-A8h] BYREF

  STRA::STRA((STRA *)v9, v12, 0x80u);
  if ( !*((_DWORD *)this + 7) && a2 )
  {
    if ( a3 )
    {
      if ( !a2[a3 - 1] )
        --a3;
      LODWORD(v6) = a3;
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
    }
    if ( (int)STRA::CopyWToUTF8Unescaped((STRA *)v9, a2, v6) >= 0 )
    {
      Memory = FREB_XML_SERIALIZER::AllocateMemory(this, Size);
      if ( Memory )
        memcpy_0(Memory, Src, (unsigned int)Size);
      else
        *((_DWORD *)this + 7) = -2147024888;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)this + 7) = LastError;
    }
  }
  STRA::~STRA((STRA *)v9);
}

```

## disassembly

```asm
0x180009360  mov     [rsp+arg_18], rbx
0x180009365  push    rbp
0x180009366  push    rsi
0x180009367  push    rdi
0x180009368  sub     rsp, 0F0h
0x18000936f  mov     rax, cs:__security_cookie
0x180009376  xor     rax, rsp
0x180009379  mov     [rsp+108h+var_28], rax
0x180009381  mov     ebx, r8d
0x180009384  mov     rsi, rdx
0x180009387  mov     rdi, rcx
0x18000938a  lea     rdx, [rsp+108h+var_A8]
0x18000938f  mov     r8d, 80h
0x180009395  lea     rcx, [rsp+108h+var_E8]
0x18000939a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800093a0  xor     ebp, ebp
0x1800093a2  cmp     [rdi+1Ch], ebp
0x1800093a5  jnz     short loc_180009422
0x1800093a7  test    rsi, rsi
0x1800093aa  jz      short loc_180009422
0x1800093ac  test    ebx, ebx
0x1800093ae  jnz     short loc_1800093C0
0x1800093b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800093b4  inc     r8
0x1800093b7  cmp     [rsi+r8*2], bp
0x1800093bc  jnz     short loc_1800093B4
0x1800093be  jmp     short loc_1800093CD
0x1800093c0  lea     ecx, [rbx-1]
0x1800093c3  cmp     [rsi+rcx*2], bp
0x1800093c7  cmovz   ebx, ecx
0x1800093ca  mov     r8d, ebx
0x1800093cd  mov     rdx, rsi
0x1800093d0  lea     rcx, [rsp+108h+var_E8]
0x1800093d5  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x1800093db  test    eax, eax
0x1800093dd  jns     short loc_1800093F6
0x1800093df  call    cs:__imp_GetLastError
0x1800093e5  test    eax, eax
0x1800093e7  jle     short loc_1800093F1
0x1800093e9  movzx   eax, ax
0x1800093ec  or      eax, 80070000h
0x1800093f1  mov     [rdi+1Ch], eax
0x1800093f4  jmp     short loc_180009422
0x1800093f6  mov     edx, dword ptr [rsp+108h+Size]; unsigned int
0x1800093fa  mov     rcx, rdi; this
0x1800093fd  call    ?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z; FREB_XML_SERIALIZER::AllocateMemory(ulong)
0x180009402  test    rax, rax
0x180009405  jnz     short loc_180009410
0x180009407  mov     dword ptr [rdi+1Ch], 80070008h
0x18000940e  jmp     short loc_180009422
0x180009410  mov     r8d, dword ptr [rsp+108h+Size]; Size
0x180009415  mov     rcx, rax; void *
0x180009418  mov     rdx, [rsp+108h+Src]; Src
0x18000941d  call    memcpy_0
0x180009422  lea     rcx, [rsp+108h+var_E8]
0x180009427  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000942d  mov     rcx, [rsp+108h+var_28]
0x180009435  xor     rcx, rsp; StackCookie
0x180009438  call    __security_check_cookie
0x18000943d  mov     rbx, [rsp+108h+arg_18]
0x180009445  add     rsp, 0F0h
0x18000944c  pop     rdi
0x18000944d  pop     rsi
0x18000944e  pop     rbp
0x18000944f  retn
```
