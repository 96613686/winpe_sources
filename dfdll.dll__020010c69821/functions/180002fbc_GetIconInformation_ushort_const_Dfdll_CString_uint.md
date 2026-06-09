# GetIconInformation(ushort const *,Dfdll::CString &,uint &)

- ea: `0x180002fbc`
- end: `0x180002ff8`
- name: `?GetIconInformation@@YAJPEBGAEAVCString@Dfdll@@AEAI@Z`
- size: `60`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Dfdll::CString *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800072e0`
- `0x1800073d0`

## callees

- `0x180002fbc`
- `0x180002ff8`
- `0x180004bcc`

## pseudocode

```c
__int64 __fastcall GetIconInformation(const unsigned __int16 *a1, struct Dfdll::CString *a2, unsigned int *a3)
{
  __int64 result; // rax

  result = TryLoadingIconInformationFromShortcut(a1, a2, a3);
  if ( (int)result < 0 )
  {
    result = Dfdll::CSystem::GetModuleFileNameW(g_hModule, a2);
    if ( (int)result >= 0 )
    {
      *a3 = 0;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002fbc  mov     [rsp+arg_0], rbx
0x180002fc1  push    rdi
0x180002fc2  sub     rsp, 20h
0x180002fc6  mov     rbx, r8
0x180002fc9  mov     rdi, rdx
0x180002fcc  call    ?TryLoadingIconInformationFromShortcut@@YAJPEBGAEAVCString@Dfdll@@AEAI@Z; TryLoadingIconInformationFromShortcut(ushort const *,Dfdll::CString &,uint &)
0x180002fd1  test    eax, eax
0x180002fd3  jns     short loc_180002FED
0x180002fd5  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180002fdc  mov     rdx, rdi; this
0x180002fdf  call    ?GetModuleFileNameW@CSystem@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z; Dfdll::CSystem::GetModuleFileNameW(HINSTANCE__ *,Dfdll::CString &)
0x180002fe4  test    eax, eax
0x180002fe6  js      short loc_180002FED
0x180002fe8  and     dword ptr [rbx], 0
0x180002feb  xor     eax, eax
0x180002fed  mov     rbx, [rsp+28h+arg_0]
0x180002ff2  add     rsp, 20h
0x180002ff6  pop     rdi
0x180002ff7  retn
```
