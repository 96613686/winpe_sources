# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x18000986c`
- end: `0x180009933`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009774`

## callees

- `0x180008d88`
- `0x18000986c`
- `0x18000993c`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rcx
  char v4; // bl
  _BYTE v6[32]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  _BYTE v8[56]; // [rsp+50h] [rbp-38h] BYREF

  if ( *((_BYTE *)a2 + 32) )
  {
    FileInSubFolder = uus::Utility::FindFileInSubFolder((std::filesystem::path *)v8, a2);
    v4 = 5;
  }
  else
  {
    v7 = 0;
    FileInSubFolder = (std::filesystem::path *)v6;
    v4 = 6;
  }
  *(_BYTE *)(a1 + 32) = 0;
  if ( *((_BYTE *)FileInSubFolder + 32) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)FileInSubFolder;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)FileInSubFolder + 1);
    *(_WORD *)FileInSubFolder = 0;
    *((_QWORD *)FileInSubFolder + 2) = 0;
    *((_QWORD *)FileInSubFolder + 3) = 7;
    *(_BYTE *)(a1 + 32) = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v7 )
      std::wstring::~wstring(v6);
  }
  if ( (v4 & 1) != 0 && v8[32] )
    std::wstring::~wstring(v8);
  return a1;
}

```

## disassembly

```asm
0x18000986c  mov     [rsp+arg_0], rbx
0x180009871  push    rdi
0x180009872  sub     rsp, 80h
0x180009879  cmp     byte ptr [rdx+20h], 0
0x18000987d  mov     rdi, rcx
0x180009880  mov     [rsp+88h+var_68], 0
0x180009888  jz      short loc_18000989E
0x18000988a  lea     rcx, [rsp+88h+var_38]; this
0x18000988f  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x180009894  mov     rcx, rax
0x180009897  mov     ebx, 5
0x18000989c  jmp     short loc_1800098AD
0x18000989e  mov     [rsp+88h+var_40], 0
0x1800098a3  lea     rcx, [rsp+88h+var_60]
0x1800098a8  mov     ebx, 6
0x1800098ad  mov     byte ptr [rdi+20h], 0
0x1800098b1  cmp     byte ptr [rcx+20h], 0
0x1800098b5  jz      short loc_1800098F0
0x1800098b7  xorps   xmm0, xmm0
0x1800098ba  xor     eax, eax
0x1800098bc  movups  xmmword ptr [rdi], xmm0
0x1800098bf  mov     qword ptr [rdi+10h], 0
0x1800098c7  mov     qword ptr [rdi+18h], 0
0x1800098cf  movups  xmm0, xmmword ptr [rcx]
0x1800098d2  movups  xmmword ptr [rdi], xmm0
0x1800098d5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800098d9  movups  xmmword ptr [rdi+10h], xmm1
0x1800098dd  mov     [rcx], ax
0x1800098e0  mov     [rcx+10h], rax
0x1800098e4  mov     qword ptr [rcx+18h], 7
0x1800098ec  mov     byte ptr [rdi+20h], 1
0x1800098f0  test    bl, 2
0x1800098f3  jz      short loc_180009909
0x1800098f5  and     ebx, 0FFFFFFFDh
0x1800098f8  cmp     [rsp+88h+var_40], 0
0x1800098fd  jz      short loc_180009909
0x1800098ff  lea     rcx, [rsp+88h+var_60]
0x180009904  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009909  test    bl, 1
0x18000990c  jz      short loc_18000991F
0x18000990e  cmp     [rsp+88h+var_18], 0
0x180009913  jz      short loc_18000991F
0x180009915  lea     rcx, [rsp+88h+var_38]
0x18000991a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000991f  mov     rbx, [rsp+88h+arg_0]
0x180009927  mov     rax, rdi
0x18000992a  add     rsp, 80h
0x180009931  pop     rdi
0x180009932  retn
```
