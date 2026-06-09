# CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)

- ea: `0x18003282c`
- end: `0x180032996`
- name: `?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z`
- size: `362`
- prototype: `void __fastcall(struct TI_ADDRESS_INFO *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180032a38`

## callees

- `0x180002890`
- `0x180003474`
- `0x18003282c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003289e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003289e`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x1800328c8`
- `api-ms-win-core-memory-l1-1-0!VirtualQueryEx` at `0x1800328c8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180032918`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180032918`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800328f2`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800328f2`

## pseudocode

```c
void __fastcall CTIPlugin::FillCallInfo(struct TI_ADDRESS_INFO *a1, void *a2, void *a3, int a4)
{
  char *v8; // rdx
  BOOL ProcessMemory; // eax
  BOOL i; // eax
  int modBaseAddr; // r8d
  __int64 v12; // rcx
  WCHAR *szExePath; // r9
  __int64 v14; // rdx
  _WORD *v15; // rax
  _WORD *v16; // rcx
  SIZE_T NumberOfBytesRead[2]; // [rsp+30h] [rbp-488h] BYREF
  MODULEENTRY32W me; // [rsp+40h] [rbp-478h] BYREF

  memset_0(&me, 0, sizeof(me));
  v8 = *(char **)a1;
  NumberOfBytesRead[0] = 0;
  *((_DWORD *)a1 + 165) = 128;
  if ( !a4 )
    v8 -= 64;
  ProcessMemory = ReadProcessMemory(a2, v8, (char *)a1 + 532, 0x80u, NumberOfBytesRead);
  *((_DWORD *)a1 + 165) = ProcessMemory ? LODWORD(NumberOfBytesRead[0]) : 0;
  if ( VirtualQueryEx(a2, *(LPCVOID *)a1, (PMEMORY_BASIC_INFORMATION)((char *)a1 + 664), 0x30u) != 48 )
  {
    *(_OWORD *)((char *)a1 + 664) = 0;
    *(_OWORD *)((char *)a1 + 680) = 0;
    *(_OWORD *)((char *)a1 + 696) = 0;
  }
  me.dwSize = 1080;
  for ( i = Module32FirstW(a3, &me); i; i = Module32NextW(a3, &me) )
  {
    modBaseAddr = (int)me.modBaseAddr;
    if ( (BYTE *)*(_QWORD *)a1 >= me.modBaseAddr
      && (BYTE *)*(_QWORD *)a1 < &me.modBaseAddr[(unsigned __int64)me.modBaseSize] )
    {
      v12 = 2147483646;
      szExePath = me.szExePath;
      v14 = 260;
      v15 = (_WORD *)((char *)a1 + 8);
      do
      {
        if ( !v12 )
          break;
        if ( !*szExePath )
          break;
        *v15++ = *szExePath++;
        --v12;
        --v14;
      }
      while ( v14 );
      v16 = v15 - 1;
      if ( v14 )
        v16 = v15;
      *v16 = 0;
      *((_DWORD *)a1 + 132) = *(_DWORD *)a1 - modBaseAddr;
      return;
    }
  }
}

```

## disassembly

```asm
0x18003282c  push    rbx
0x18003282e  push    rbp
0x18003282f  push    rsi
0x180032830  push    rdi
0x180032831  push    r14
0x180032833  sub     rsp, 490h
0x18003283a  mov     rax, cs:__security_cookie
0x180032841  xor     rax, rsp
0x180032844  mov     [rsp+4B8h+var_38], rax
0x18003284c  mov     rsi, r8
0x18003284f  mov     rbp, rdx
0x180032852  mov     rdi, rcx
0x180032855  xor     edx, edx; Val
0x180032857  mov     r8d, 438h; Size
0x18003285d  lea     rcx, [rsp+4B8h+me]; void *
0x180032862  mov     ebx, r9d
0x180032865  call    memset_0
0x18003286a  mov     rdx, [rdi]
0x18003286d  xor     r14d, r14d
0x180032870  mov     [rsp+4B8h+NumberOfBytesRead], r14
0x180032875  mov     r9d, 80h; nSize
0x18003287b  mov     [rdi+294h], r9d
0x180032882  test    ebx, ebx
0x180032884  jnz     short loc_18003288A
0x180032886  add     rdx, 0FFFFFFFFFFFFFFC0h; lpBaseAddress
0x18003288a  lea     rax, [rsp+4B8h+NumberOfBytesRead]
0x18003288f  mov     rcx, rbp; hProcess
0x180032892  lea     r8, [rdi+214h]; lpBuffer
0x180032899  mov     [rsp+4B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003289e  call    cs:__imp_ReadProcessMemory
0x1800328a4  lea     rbx, [rdi+298h]
0x1800328ab  mov     r9d, 30h ; '0'; dwLength
0x1800328b1  neg     eax
0x1800328b3  mov     r8, rbx; lpBuffer
0x1800328b6  mov     rcx, rbp; hProcess
0x1800328b9  sbb     edx, edx
0x1800328bb  and     edx, dword ptr [rsp+4B8h+NumberOfBytesRead]
0x1800328bf  mov     [rdi+294h], edx
0x1800328c5  mov     rdx, [rdi]; lpAddress
0x1800328c8  call    cs:__imp_VirtualQueryEx
0x1800328ce  cmp     rax, 30h ; '0'
0x1800328d2  jz      short loc_1800328E2
0x1800328d4  xorps   xmm0, xmm0
0x1800328d7  movups  xmmword ptr [rbx], xmm0
0x1800328da  movups  xmmword ptr [rbx+10h], xmm0
0x1800328de  movups  xmmword ptr [rbx+20h], xmm0
0x1800328e2  lea     rdx, [rsp+4B8h+me]; lpme
0x1800328e7  mov     [rsp+4B8h+me.dwSize], 438h
0x1800328ef  mov     rcx, rsi; hSnapshot
0x1800328f2  call    cs:__imp_Module32FirstW
0x1800328f8  jmp     short loc_18003291E
0x1800328fa  mov     r8, [rsp+4B8h+me.modBaseAddr]
0x1800328ff  cmp     [rdi], r8
0x180032902  jb      short loc_180032910
0x180032904  mov     eax, [rsp+4B8h+me.modBaseSize]
0x180032908  add     rax, r8
0x18003290b  cmp     [rdi], rax
0x18003290e  jb      short loc_180032924
0x180032910  lea     rdx, [rsp+4B8h+me]; lpme
0x180032915  mov     rcx, rsi; hSnapshot
0x180032918  call    cs:__imp_Module32NextW
0x18003291e  test    eax, eax
0x180032920  jnz     short loc_1800328FA
0x180032922  jmp     short loc_180032978
0x180032924  mov     ecx, 7FFFFFFEh
0x180032929  lea     r9, [rsp+4B8h+me.szExePath]
0x180032931  mov     edx, 104h
0x180032936  lea     rax, [rdi+8]
0x18003293a  test    rcx, rcx
0x18003293d  jz      short loc_18003295E
0x18003293f  movzx   r10d, word ptr [r9]
0x180032943  test    r10w, r10w
0x180032947  jz      short loc_18003295E
0x180032949  mov     [rax], r10w
0x18003294d  add     r9, 2
0x180032951  add     rax, 2
0x180032955  dec     rcx
0x180032958  sub     rdx, 1
0x18003295c  jnz     short loc_18003293A
0x18003295e  lea     rcx, [rax-2]
0x180032962  test    rdx, rdx
0x180032965  cmovnz  rcx, rax
0x180032969  mov     [rcx], r14w
0x18003296d  mov     eax, [rdi]
0x18003296f  sub     eax, r8d
0x180032972  mov     [rdi+210h], eax
0x180032978  mov     rcx, [rsp+4B8h+var_38]
0x180032980  xor     rcx, rsp; StackCookie
0x180032983  call    __security_check_cookie
0x180032988  add     rsp, 490h
0x18003298f  pop     r14
0x180032991  pop     rdi
0x180032992  pop     rsi
0x180032993  pop     rbp
0x180032994  pop     rbx
0x180032995  retn
```
