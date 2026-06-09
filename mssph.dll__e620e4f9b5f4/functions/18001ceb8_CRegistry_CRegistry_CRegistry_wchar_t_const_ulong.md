# CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)

- ea: `0x18001ceb8`
- end: `0x18001cf87`
- name: `??0CRegistry@@QEAA@PEAV0@PEB_WK@Z`
- size: `207`
- prototype: `CRegistry *__fastcall(CRegistry *this, HKEY *, const wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001c960`
- `0x18001cab0`
- `0x18001d2f0`
- `0x18001dae0`

## callees

- `0x18000a100`
- `0x18000a210`
- `0x18000d924`
- `0x18000e488`
- `0x18001ceb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cf15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cf6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cf15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cf6a`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, HKEY *a2, const wchar_t *a3, unsigned int a4)
{
  struct CLMString *v8; // rbx
  const wchar_t *v9; // rcx
  unsigned int v10; // r9d
  DWORD v11; // eax

  v8 = (CRegistry *)((char *)this + 8);
  *((_QWORD *)this + 2) = (char *)this + 32;
  *((_QWORD *)this + 3) = 65;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 1) = &TLMString<64,64,32767>::`vftable';
  *(_QWORD *)this = &CRegistry::`vftable';
  *((_DWORD *)this + 42) = 1;
  SetLastError(0);
  TLMString<64,64,32767>::operator=(v8, a2 + 1);
  AppendSlashIf(v8);
  CLMString::Append(v8, a3, 0xFFFFFFFF);
  v11 = WSearchRegOpenKeyEx(v9, a2[22], a3, v10, a4, (HKEY *)this + 22);
  if ( v11 )
  {
    *((_QWORD *)this + 22) = 0;
    SetLastError(v11);
  }
  return this;
}

```

## disassembly

```asm
0x18001ceb8  mov     [rsp+arg_8], rbx
0x18001cebd  mov     [rsp+arg_10], rbp
0x18001cec2  mov     [rsp+arg_0], rcx
0x18001cec7  push    rsi
0x18001cec8  push    rdi
0x18001cec9  push    r14
0x18001cecb  sub     rsp, 30h
0x18001cecf  mov     edi, r9d
0x18001ced2  mov     rsi, r8
0x18001ced5  mov     rbp, rdx
0x18001ced8  mov     r14, rcx
0x18001cedb  lea     rbx, [rcx+8]
0x18001cedf  lea     r10, [rbx+18h]
0x18001cee3  mov     [rbx+8], r10
0x18001cee7  mov     qword ptr [rbx+10h], 41h ; 'A'
0x18001ceef  xor     eax, eax
0x18001cef1  mov     [r10], ax
0x18001cef5  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18001cefc  mov     [rbx], rax
0x18001ceff  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18001cf06  mov     [rcx], rax
0x18001cf09  mov     dword ptr [rcx+0A8h], 1
0x18001cf13  xor     ecx, ecx; dwErrCode
0x18001cf15  call    cs:__imp_SetLastError
0x18001cf1b  lea     rdx, [rbp+8]
0x18001cf1f  mov     rcx, rbx
0x18001cf22  call    ??4?$TLMString@$0EA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<64,64,32767>::operator=(TLMString<64,64,32767> const &)
0x18001cf27  mov     rcx, rbx; this
0x18001cf2a  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x18001cf2f  or      r8d, 0FFFFFFFFh; unsigned int
0x18001cf33  mov     rdx, rsi; wchar_t *
0x18001cf36  mov     rcx, rbx; this
0x18001cf39  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18001cf3e  lea     rbx, [r14+0B0h]
0x18001cf45  mov     [rsp+48h+var_20], rbx; HKEY *
0x18001cf4a  mov     [rsp+48h+var_28], edi; unsigned int
0x18001cf4e  mov     r8, rsi; wchar_t *
0x18001cf51  mov     rdx, [rbp+0B0h]; HKEY
0x18001cf58  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18001cf5d  test    eax, eax
0x18001cf5f  jz      short loc_18001CF71
0x18001cf61  mov     qword ptr [rbx], 0
0x18001cf68  mov     ecx, eax; dwErrCode
0x18001cf6a  call    cs:__imp_SetLastError
0x18001cf70  nop
0x18001cf71  mov     rax, r14
0x18001cf74  mov     rbx, [rsp+48h+arg_8]
0x18001cf79  mov     rbp, [rsp+48h+arg_10]
0x18001cf7e  add     rsp, 30h
0x18001cf82  pop     r14
0x18001cf84  pop     rdi
0x18001cf85  pop     rsi
0x18001cf86  retn
```
