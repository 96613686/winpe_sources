# DepFSPostCreate

- ea: `0x180008c10`
- end: `0x180008d56`
- name: `DepFSPostCreate`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001020`
- `0x18000844c`
- `0x1800084f4`
- `0x180008c10`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cfd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cbe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008cb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008cf1`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008cb2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008cf1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008c66`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008c66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008c51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008c51`

## pseudocode

```c
__int64 __fastcall DepFSPostCreate(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v11[0] = 0;
  if ( (a4 & 1) == 0 )
  {
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL);
    if ( v6 )
    {
      if ( (*(_DWORD *)(v6 + 80) & 0x400000) != 0 )
      {
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(&Resource, 1u);
        v7 = DepFSFindOurVolumeContext(*(_QWORD *)(a2 + 16), v11);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_a4016d7e857d3af68560d770380f4c36_Traceguids,
              (unsigned int)v7);
          }
        }
        else
        {
          if ( *(int *)(a1 + 24) >= 0 )
          {
            v9 = *(_QWORD *)(a1 + 16);
            v8 = v11[0];
            *(_QWORD *)(v11[0] + 104) = *(_QWORD *)(v9 + 8);
            *(_DWORD *)(v8 + 96) = 2;
            ExReleaseResourceLite(&Resource);
            KeLeaveCriticalRegion();
          }
          else
          {
            v8 = v11[0];
            *(_DWORD *)(v11[0] + 96) = 16;
            *(_QWORD *)(v8 + 104) = 0;
            --dword_18000518C;
            ExReleaseResourceLite(&Resource);
            KeLeaveCriticalRegion();
            DepFSHandleAutochkForHostVolume(v8, 2);
          }
          DereferenceVolumeContext(v8);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008c10  mov     [rsp+arg_0], rbx
0x180008c15  push    rdi
0x180008c16  sub     rsp, 30h
0x180008c1a  mov     [rsp+38h+var_18], 0
0x180008c23  mov     rdi, rdx
0x180008c26  mov     rbx, rcx
0x180008c29  test    r9b, 1
0x180008c2d  jnz     loc_180008D48
0x180008c33  mov     rax, [rcx+10h]
0x180008c37  mov     rax, [rax+8]
0x180008c3b  test    rax, rax
0x180008c3e  jz      loc_180008D48
0x180008c44  test    dword ptr [rax+50h], 400000h
0x180008c4b  jz      loc_180008D48
0x180008c51  call    cs:__imp_KeEnterCriticalRegion
0x180008c58  nop     dword ptr [rax+rax+00h]
0x180008c5d  mov     dl, 1; Wait
0x180008c5f  lea     rcx, Resource; Resource
0x180008c66  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008c6d  nop     dword ptr [rax+rax+00h]
0x180008c72  mov     rcx, [rdi+10h]
0x180008c76  lea     rdx, [rsp+38h+var_18]
0x180008c7b  call    DepFSFindOurVolumeContext
0x180008c80  mov     r9d, eax
0x180008c83  test    eax, eax
0x180008c85  js      loc_180008D13
0x180008c8b  cmp     dword ptr [rbx+18h], 0
0x180008c8f  lea     rcx, Resource; Resource
0x180008c96  jge     short loc_180008CD9
0x180008c98  mov     rbx, [rsp+38h+var_18]
0x180008c9d  mov     dword ptr [rbx+60h], 10h
0x180008ca4  mov     qword ptr [rbx+68h], 0
0x180008cac  dec     cs:dword_18000518C
0x180008cb2  call    cs:__imp_ExReleaseResourceLite
0x180008cb9  nop     dword ptr [rax+rax+00h]
0x180008cbe  call    cs:__imp_KeLeaveCriticalRegion
0x180008cc5  nop     dword ptr [rax+rax+00h]
0x180008cca  mov     edx, 2
0x180008ccf  mov     rcx, rbx
0x180008cd2  call    DepFSHandleAutochkForHostVolume
0x180008cd7  jmp     short loc_180008D09
0x180008cd9  mov     rax, [rbx+10h]
0x180008cdd  mov     rbx, [rsp+38h+var_18]
0x180008ce2  mov     rdx, [rax+8]
0x180008ce6  mov     [rbx+68h], rdx
0x180008cea  mov     dword ptr [rbx+60h], 2
0x180008cf1  call    cs:__imp_ExReleaseResourceLite
0x180008cf8  nop     dword ptr [rax+rax+00h]
0x180008cfd  call    cs:__imp_KeLeaveCriticalRegion
0x180008d04  nop     dword ptr [rax+rax+00h]
0x180008d09  mov     rcx, rbx
0x180008d0c  call    DereferenceVolumeContext
0x180008d11  jmp     short loc_180008D48
0x180008d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d1a  lea     rax, WPP_GLOBAL_Control
0x180008d21  cmp     rcx, rax
0x180008d24  jz      short loc_180008D48
0x180008d26  mov     eax, [rcx+2Ch]
0x180008d29  test    al, 1
0x180008d2b  jz      short loc_180008D48
0x180008d2d  cmp     byte ptr [rcx+29h], 2
0x180008d31  jb      short loc_180008D48
0x180008d33  mov     rcx, [rcx+18h]
0x180008d37  lea     r8, WPP_a4016d7e857d3af68560d770380f4c36_Traceguids
0x180008d3e  mov     edx, 0Dh
0x180008d43  call    WPP_SF_D
0x180008d48  mov     rbx, [rsp+38h+arg_0]
0x180008d4d  xor     eax, eax
0x180008d4f  add     rsp, 30h
0x180008d53  pop     rdi
0x180008d54  retn
```
