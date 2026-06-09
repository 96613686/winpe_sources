# win_musl::FiberStream<win_musl::FiberStreamClient<win_musl::consumption::ContainerSender,win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>>>::TransferToFiber(void)

- ea: `0x180047238`
- end: `0x180047373`
- name: `?TransferToFiber@?$FiberStream@V?$FiberStreamClient@VContainerSender@consumption@win_musl@@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@win_musl@@@win_musl@@AEAAXXZ`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004719c`
- `0x180047704`

## callees

- `0x180001de4`
- `0x180004680`
- `0x180015660`
- `0x180031218`
- `0x180047238`
- `0x1800474b4`
- `0x1800475b0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180047367`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180047367`

## string_xrefs

- `0x180047360`: `win_musl::FiberStream<class win_musl::FiberStreamClient<class win_musl::consumption::ContainerSender,class win_scope::scope<class win_musl::consumption::ContainerSender *,struct win_scope::const_policies<struct win_scope::com_policies> > > >::TransferToFiber, m_pCommandDerecurser->IsRecursed() is true, must call command syncronously for the data copy to work!\n`

## pseudocode

```c

```
